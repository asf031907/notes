# STEP 10 — Coding Architecture v1.0

এই ধাপের উদ্দেশ্য হলো এক লাইনে Pine code লেখার আগে পুরো engine-টাকে software হিসেবে কীভাবে build করব সেটা lock করা। এরপর Claude-কে coding দেওয়া হবে।

---

## 10.1 Build strategy: একবারে 2,000+ line code নয়

এখানে একটা blind spot আছে: সরাসরি পুরো Master Engine Claude-কে দিলে Claude সাধারণত দ্রুত code লিখে ফেলবে, কিন্তু পরে repaint, MTF synchronization, state reset, object overflow এবং source-logic drift debug করা কঠিন হবে।

তাই আমরা modular build + integration করব:

| Build | Module | উদ্দেশ্য |
|---|---|---|
| 1 | Core + Data Layer | MTF data safely আনা |
| 2 | Context Engine | 1W/1D bias |
| 3 | Liquidity Engine | HTF liquidity |
| 4 | Sweep + Reclaim | event detection |
| 5 | CISD/MSS | structure |
| 6 | Displacement | normalized strength |
| 7 | FVG/IFVG/Breaker/Unicorn | POI |
| 8 | SMT | XAU ↔ XAG |
| 9 | Regime | session/volatility |
| 10 | 30M Execution | final trigger |
| 11 | Signal + Alerts | output |
| 12 | Visual + Debug | chart interface |
| 13 | Backtest Harness | validation |

কিন্তু এগুলো ১৩টি আলাদা STEP নয়। এগুলো STEP 10-এর coding architecture-এর internal build order।

---

## 10.2 File architecture

Pine Script-এর limitation-এর কারণে আমরা প্রথমে conceptual modules আলাদা রাখব, কিন্তু final TradingView indicator একটি single `.pine` script হবে।

Structure:

<pre><code>MASTER_ENGINE.pine

// 01 CONFIG
// 02 DATA LAYER
// 03 UTILITY FUNCTIONS
// 04 CONTEXT ENGINE
// 05 LIQUIDITY ENGINE
// 06 SWEEP ENGINE
// 07 RECLAIM ENGINE
// 08 STRUCTURE ENGINE
// 09 DISPLACEMENT ENGINE
// 10 SMT ENGINE
// 11 POI ENGINE
// 12 REGIME ENGINE
// 13 EXECUTION ENGINE
// 14 SIGNAL ENGINE
// 15 RISK ENGINE
// 16 VISUAL ENGINE
// 17 ALERT ENGINE
// 18 DEBUG ENGINE
// 19 BACKTEST ENGINE
</code></pre>

এতে পরে কোনো bug হলে আমরা জানব bug কোন subsystem-এ।

---

## 10.3 Input architecture

User-facing inputs অতিরিক্ত হবে না।

**Core**
<pre><code>Enable Master Engine
Execution TF
Context TF
</code></pre>

**Detection**
<pre><code>Swing Sensitivity
Liquidity Sensitivity
Displacement Threshold
POI Lifetime
Setup Expiry
</code></pre>

**SMT**
<pre><code>Enable SMT
SMT Symbol
SMT Matching Window
</code></pre>

**Regime**
<pre><code>Session Filter
Volatility Filter
News Block
</code></pre>

**Execution**
<pre><code>Execution Confirmation
Minimum Quality
</code></pre>

**Risk**
<pre><code>Risk %
SL Buffer
TP Mode
</code></pre>

**Visual**
<pre><code>Show Context
Show Liquidity
Show POI
Show SMT
Show Signals
Debug Mode
</code></pre>

---

## 10.4 Data Layer

এটা engine-এর foundation।

Default:
<pre><code>Chart = 30M
</code></pre>

তারপর:
<pre><code>request.security()
</code></pre>

এর মাধ্যমে:
<pre><code>1H
4H
1D
1W
</code></pre>

এবং SMT-এর জন্য:
<pre><code>XAGUSD
</code></pre>

data আসবে।

TradingView-এর official documentation অনুযায়ী HTF request-এর ক্ষেত্রে confirmed values ব্যবহার করতে হবে যাতে historical বনাম realtime behaviour mismatch এবং lookahead bias এড়ানো যায়।

**Hard rule**
<pre><code>NO LOOKAHEAD
NO FUTURE LEAK
NO UNCONFIRMED HTF SIGNAL
</code></pre>

---

## 10.5 Context Engine

Input:
<pre><code>1W
1D
</code></pre>

Output:
<pre><code>BULLISH
BEARISH
NEUTRAL
TRANSITION
</code></pre>

এখানে context শুধু permission layer। এটি সরাসরি entry তৈরি করবে না।

<pre><code>Context
  ↓
Permission
</code></pre>

not:
<pre><code>Context
  ↓
BUY
</code></pre>

---

## 10.6 Liquidity Engine

এটি active liquidity objects maintain করবে।

প্রতিটি level-এর internal state:
<pre><code>type
price
timeframe
strength
createdTime
status
</code></pre>

Status:
<pre><code>ACTIVE
SWEPT
CONSUMED
EXPIRED
</code></pre>

---

## 10.7 Sweep Engine

Liquidity Engine বলে:
> "এই level আছে।"

Sweep Engine বলে:
> "Price এই level-কে raid করেছে।"

এ দুটো আলাদা রাখা হচ্ছে।

<pre><code>LIQUIDITY
  ↓
SWEEP
</code></pre>

---

## 10.8 Reclaim Engine

Sweep হওয়ার পর:
<pre><code>WAIT_RECLAIM
</code></pre>

তারপর:
<pre><code>RECLAIM_CONFIRMED
</code></pre>

অথবা:
<pre><code>FAILED
</code></pre>

**Critical**

Sweep এবং reclaim একই candle-এ হলে source definition অনুযায়ী handling আলাদা হতে পারে।

তাই coding-এর আগে source-specific rules যেখানে ambiguous, Claude নিজে assumption করবে না।

---

## 10.9 Structure Engine

এখানে:
<pre><code>CISD
MSS
</code></pre>
থাকবে।

Output:
<pre><code>BULLISH_STRUCTURE
BEARISH_STRUCTURE
NONE
</code></pre>

**Important**

CISD/MSS দুইটা signal যোগ করে
<pre><code>+2
</code></pre>
করা হবে না।

বরং:
<pre><code>CISD
  OR
MSS
  ↓
STRUCTURE_CONFIRMED
</code></pre>

---

## 10.10 Displacement Engine

Displacement:
<pre><code>price movement
÷
volatility baseline
</code></pre>
দিয়ে normalize হবে।

Output:
<pre><code>WEAK
VALID
STRONG
</code></pre>

এখানে threshold input থাকবে।

এখনই threshold optimize করা হবে না। কারণ সেটা backtest-এর কাজ।

---

## 10.11 POI Engine

একই engine-এর মধ্যে:
<pre><code>FVG
IFVG
Breaker
Unicorn
Turtle Soup
</code></pre>
থাকবে।

কিন্তু hierarchy থাকবে:
<pre><code>EVENT
  ↓
POI
</code></pre>

এবং duplicate counting বন্ধ থাকবে।

---

## 10.12 SMT Engine

Default pair:
<pre><code>XAUUSD
XAGUSD
</code></pre>

Output:
<pre><code>ALIGNED
NEUTRAL
CONTRADICTORY
</code></pre>

SMT-এর role:
<pre><code>Evidence
</code></pre>

not:
<pre><code>Trigger
</code></pre>

**Hard rule**

SMT absent:
<pre><code>NOT AUTOMATICALLY BLOCKED
</code></pre>

SMT contradictory:
<pre><code>QUALITY DOWN / POSSIBLE BLOCK
</code></pre>

---

## 10.13 Regime Engine

দুটি independent dimensions:
<pre><code>SESSION
+
VOLATILITY
</code></pre>

Session:
<pre><code>ASIA
LONDON
NY
LONDON_CLOSE
OFF_SESSION
</code></pre>

Volatility:
<pre><code>NORMAL
ELEVATED
EXTREME
</code></pre>

তারপর:
<pre><code>REGIME_ALLOWED
</code></pre>
বা:
<pre><code>REGIME_BLOCKED
</code></pre>

---

## 10.14 Execution Engine

এখানে সবচেয়ে important gate:
<pre><code>HTF Thesis
   ↓
4H Event
   ↓
1H Structure
   ↓
POI
   ↓
30M Confirmation
</code></pre>

তারপর:
<pre><code>EXECUTION_READY
</code></pre>

এটাই actual entry architecture।

---

## 10.15 Signal Engine

Signal engine raw indicators plot করবে না।

এটা final state তৈরি করবে:
<pre><code>WAIT
LONG_CANDIDATE
SHORT_CANDIDATE
LONG_ENTRY
SHORT_ENTRY
INVALIDATED
EXPIRED
</code></pre>

---

## 10.16 Risk Engine

Risk engine signal-এর direction বদলাবে না।

এটি calculate করবে:
<pre><code>Entry
SL
TP
R:R
Position Size
</code></pre>

**SL** — Structural invalidation।

**TP** — Liquidity-based।

---

## 10.17 Visual Engine

Chart-এর default display:

- **1W / 1D** — Context
- **4H** — Liquidity + Sweep
- **1H** — Structure + POI
- **30M** — Execution

এভাবে chart readable থাকবে।

---

## 10.18 Debug Engine

এটা mandatory।

Debug mode ON:
<pre><code>CONTEXT: BULLISH
4H LIQUIDITY: SSL
SWEEP: YES
RECLAIM: YES
STRUCTURE: CISD BULL
DISPLACEMENT: VALID
SMT: ALIGNED
POI: UNICORN
30M: CONFIRMED
FINAL: LONG
</code></pre>

এটা আমাদের সবচেয়ে powerful debugging tool হবে।

---

## 10.19 Alert Engine

Primary:
<pre><code>LONG ENTRY
SHORT ENTRY
</code></pre>

Secondary:
<pre><code>SWEEP
RECLAIM
STRUCTURE
POI TOUCH
EXECUTION READY
INVALIDATION
</code></pre>

---

## 10.20 Backtest Engine

Backtest mode-এ আমরা hypothetical trade lifecycle রাখব:
<pre><code>SIGNAL
  ↓
ENTRY
  ↓
SL / TP
  ↓
RESULT
</code></pre>

Output:
<pre><code>Trades
Wins
Losses
Win Rate
Average R
Expectancy
Profit Factor
Max Drawdown
</code></pre>

---

## 10.21 সবচেয়ে গুরুত্বপূর্ণ: State Machine

Coding-এর কেন্দ্র হবে এই state:
<pre><code>NO_SETUP
  ↓
CONTEXT_VALID
  ↓
LIQUIDITY_FOUND
  ↓
SWEEP_DETECTED
  ↓
RECLAIM_CONFIRMED
  ↓
STRUCTURE_CONFIRMED
  ↓
POI_ACTIVE
  ↓
EXECUTION_READY
  ↓
ENTRY
</code></pre>

Failure:
<pre><code>INVALIDATED
</code></pre>

Timeout:
<pre><code>EXPIRED
</code></pre>

এতে engine একই setup-এর জন্য ২টা signal ছুড়ে দেবে না।

---

## 10.22 Duplicate Signal Protection

একটি setup-এর unique ID থাকবে।

Concept:
<pre><code>setupID =
time + direction + source event
</code></pre>

যতক্ষণ setup active:
<pre><code>NO DUPLICATE ENTRY
</code></pre>

---

## 10.23 Re-entry

Default: **No automatic re-entry.**

একটি failed setup-এর পরে নতুন liquidity event / new structure event প্রয়োজন।

এটা overtrading অনেক কমাবে।

---

## 10.24 MTF Synchronization

এখানে বড় risk হলো:
<pre><code>4H event
+
1H event
+
30M event
</code></pre>

একই physical event-কে তিনটি independent event হিসেবে গণনা করা।

তাই প্রত্যেক event-এর metadata:
<pre><code>eventID
sourceTF
timestamp
direction
parentEvent
</code></pre>
রাখব।

---

## 10.25 Parent-Child Relationship

Example:
<pre><code>4H SWEEP
  |
  └─ 1H STRUCTURE
       |
       └─ 30M EXECUTION
</code></pre>

তাহলে 30M signal-এর genealogy জানা যাবে।

এটা পরে backtest analysis-এ অসাধারণ useful হবে।

---

## 10.26 Final Signal Genealogy

প্রতিটি trade-এর জন্য আমরা theoretically দেখতে পারব:

<pre><code>TRADE #001

1D  = Bullish
4H  = SSL Sweep
4H  = Reclaim
1H  = CISD Bull
1H  = Displacement Valid
POI = Unicorn
SMT = Aligned
30M = Confirmation
Entry  = X
SL     = X
TP     = X
Result = +R / -R
</code></pre>

এটাই আমাদের engine-কে researchable করবে।

---

## 10.27 Claude-এর Coding Rules

Claude-কে আমরা বলব:

| Rule | নির্দেশনা |
|---|---|
| 1 | Source-specific logic না বুঝলে assumption নয়। |
| 2 | Repainting নয়। |
| 3 | Lookahead নয়। |
| 4 | Magic numbers নয়। |
| 5 | Every threshold input-driven। |
| 6 | Duplicate event নয়। |
| 7 | Every signal traceable। |
| 8 | Compile errors নিজে diagnose করবে। |
| 9 | Performance-এর জন্য unnecessary loops avoid করবে। |
| 10 | প্রতিটি module independently testable রাখতে হবে। |

---
## 10.28 Claude-কে দেওয়ার MASTER CODING PROMPT

**এখন থেকে এটাই coding handoff document-এর foundation:**


<pre><code>You are the senior Pine Script v6 engineer responsible for implementing
the XAUUSD Master Engine.

OBJECTIVE:
Build a non-repainting, event-driven, multi-timeframe XAUUSD trading
decision engine for research, visualization and systematic backtesting.

PRIMARY MARKET:
XAUUSD

EXECUTION:
30M

DECISION TIMEFRAMES:
1H / 4H

CONTEXT:
1D / 1W

SMT:
XAUUSD vs XAGUSD

CORE PIPELINE:

1W/1D CONTEXT
→ 4H LIQUIDITY
→ LIQUIDITY SWEEP
→ RECLAIM
→ 1H CISD OR MSS
→ DISPLACEMENT
→ POI
→ SMT VALIDATION
→ 30M EXECUTION CONFIRMATION
→ SIGNAL

CORE STATES:

NO_SETUP
CONTEXT_VALID
LIQUIDITY_FOUND
SWEEP_DETECTED
RECLAIM_CONFIRMED
STRUCTURE_CONFIRMED
POI_ACTIVE
EXECUTION_READY
ENTRY
INVALIDATED
EXPIRED

MANDATORY ENGINEERING REQUIREMENTS:

1. Pine Script v6.
2. No lookahead bias.
3. No future leakage.
4. Avoid repainting wherever technically possible.
5. HTF logic must use confirmed data.
6. Do not fabricate source-specific definitions.
7. Preserve source-derived CISD/CRT/IFVG/Unicorn logic.
8. Do not double-count correlated events.
9. Use event-driven state management.
10. Prevent duplicate signals.
11. Maintain event genealogy.
12. Provide debug mode.
13. Provide alert conditions.
14. Provide optional backtest mode.
15. Keep thresholds configurable.
16. Avoid unnecessary loops and excessive drawing objects.
17. Clearly separate data, detection, decision, visual and alert layers.
18. Never claim profitability or accuracy without empirical validation.

ARCHITECTURE:

CONFIG
DATA_LAYER
UTILITY
CONTEXT_ENGINE
LIQUIDITY_ENGINE
SWEEP_ENGINE
RECLAIM_ENGINE
STRUCTURE_ENGINE
DISPLACEMENT_ENGINE
SMT_ENGINE
POI_ENGINE
REGIME_ENGINE
EXECUTION_ENGINE
SIGNAL_ENGINE
RISK_ENGINE
VISUAL_ENGINE
ALERT_ENGINE
DEBUG_ENGINE
BACKTEST_ENGINE

SIGNAL LOGIC:

LONG requires:
- bullish HTF permission
- qualified 4H sell-side liquidity
- valid sweep
- confirmed reclaim
- bullish 1H structure
- valid displacement
- valid bullish POI
- SMT not contradictory
- regime permitted
- 30M execution confirmation

SHORT is the exact bearish mirror.

IMPORTANT:

Do NOT turn every component into a score.
Use hierarchical gated logic.

SMT is validation evidence, not an independent entry trigger.

CISD and MSS confirming the same structural event must not be
double-counted.

Unicorn must not double-count its FVG and Breaker components.

STRUCTURAL SL and liquidity-based TP must remain separate from signal
generation.

Before coding:
1. Audit the specification.
2. Identify ambiguities.
3. Identify source-specific definitions that require exact source-code
verification.
4. Do not silently invent missing definitions.
5. Produce the implementation plan.

Then implement the code in controlled modules and provide compile-ready
Pine Script v6.</code></pre>

---

## STEP 10 STATUS

| Area | Status |
|---|---|
| Pine v6 architecture | 🟢 |
| Module structure | 🟢 |
| MTF architecture | 🟢 |
| State machine | 🟢 |
| Event architecture | 🟢 |
| Signal architecture | 🟢 |
| SMT architecture | 🟢 |
| POI architecture | 🟢 |
| Risk architecture | 🟢 |
| Debug architecture | 🟢 |
| Alert architecture | 🟢 |
| Backtest architecture | 🟢 |
| Claude coding framework | 🟢 |
| Exact source semantics | 🟠 |
| Numerical calibration | 🟠 |
| Final code | 🔴 |

অর্থাৎ:

**Architecture = DONE.**
**Coding = এখনো শুরু হয়নি।**

---

## ⚠️ কিন্তু এখানে আমি তোমাকে থামাচ্ছি

এই prompt এখনই Claude-এ দিয়ে final 2,000-line engine generate করা আমার recommendation নয়।

কারণ আমাদের source indicators-এর exact source-code semantics এবং কিছু implementation-specific definitions এখনও coding handoff-এর আগে normalize করতে হবে।

বিশেষ করে:

- CISD exact trigger
- CRT/C2 exact state
- IFVG lifecycle
- Unicorn exact construction
- Fractal model-এর exact role
- liquidity classification
- sweep/reclaim edge cases

এসবের মধ্যে কোনো একটি Claude নিজের মতো interpret করলে আমাদের Master Engine-এর foundation নষ্ট হতে পারে।

তাই STEP 10-এর architecture complete, কিন্তু coding handoff-এর জন্য একটি final technical gate আছে।
