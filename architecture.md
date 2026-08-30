## Architecture

<pre><code>                    XAUUSD MASTER ENGINE
                           │
             ┌─────────────┴─────────────┐
             │                           │
        MARKET CONTEXT              MARKET EVENT
             │                           │
          1W / 1D                       4H
             │                           │
       ┌─────┴─────┐              ┌─────┴─────┐
       │           │              │           │
    1W Regime   1D Bias       Liquidity    CRT
       │           │              │           │
       └─────┬─────┘              └─────┬─────┘
             │                          │
             └────────────┬─────────────┘
                          ↓
                   EVENT CONFIRMATION
                          │
                 Displacement + CISD
                          │
                          ↓
                     SMT ENGINE
                     XAU ↔ XAG
                          │
                          ↓
                    REPRICING / POI
                 ┌────────┼────────┐
                 ↓        ↓        ↓
                FVG      IFVG    Breaker
                 └────────┼────────┘
                          ↓
                    1H CONFIRMATION
                          │
                          ↓
                    30M REFINEMENT
                          │
                          ↓
                    RISK ENGINE
                    SL / TP / RR
                          │
                          ↓
                  SIGNAL STATE MACHINE
             ┌────────────┼────────────┐
             ↓            ↓            ↓
          WATCH       CONFIRMED      ENTRY
             │
             └──────── NO TRADE</code></pre>
#### সবচেয়ে গুরুত্বপূর্ণ architectural rule

**প্রতিটি module independently signal দেবে না।**

বরং upstream module-এর output downstream module-এর input হবে।

উদাহরণ:

<pre><code>30M-এ bullish FVG পাওয়া গেছে বলে Buy নয়।</code></pre>

বরং:

**HTF context → liquidity event → CISD → POI → 30M confirmation → Entry**

এই dependency chain-টাই engine-এর backbone।

### — Data Flow
আমাদের data flow হবে:

#### Layer 1 — Context

**1W → 1D**

Output:
<pre><code>REGIME
BIAS</code></pre>
#### Layer 2 — Location

**4H**

Output:
<pre><code>LIQUIDITY LOCATION
EVENT
POI CANDIDATE</code></pre>
#### Layer 3 — Confirmation

**1H**

Output:
<pre><code>DISPLACEMENT
CISD
STRUCTURAL CONFIRMATION</code></pre>
#### Layer 4 — Cross-Market Validation

**XAGUSD**

Output:
<pre><code>SMT
CONFIRMATION
CONTRADICTION
ABSENT</code></pre>
#### Layer 5 — Execution

**30M**

Output:
<pre><code>ENTRY
INVALIDATION</code></pre>
### — Core বনাম Optional Modules

এখন architecture-এর dependency পরিষ্কার করছি।

**Core**
<pre><code>1W/1D Context
4H Liquidity
1H Displacement
CISD
Risk</code></pre>
#### Execution
<pre><code>FVG
IFVG
Breaker
30M refinement</code></pre>
#### Research / Enhancement
<pre><code>CRT
SMT
Fractal</code></pre>
**কিন্তু SMT architecture-এ অবশ্যই থাকবে**, কারণ তুমি এটাকে রাখতে চেয়েছো। “Research” মানে বাদ দেওয়া নয়; এর exact weighting/requirement test করা হবে।

### — Explainability Layer

Final indicator শুধু:

**BUY**

দেখাবে না।

বরং:
<pre><code>LONG — A SETUP

1W Regime       ✓
1D Bias         ✓
4H Liquidity    ✓
Sweep           ✓
Displacement    ✓
CISD            ✓
SMT XAU/XAG     ✓
POI             IFVG
30M Confirm     ✓

SL               xxx
TP               xxx
RR               x.xx</code></pre>
আর condition না মিললে:
<pre><code>WATCH

Waiting for:
→ 1H CISD</code></pre>
এটা আমি final indicator-এর non-negotiable feature হিসেবে recommend করছি।
