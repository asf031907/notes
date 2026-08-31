এই ধাপে আমাদের লক্ষ্য indicator concepts নয়; বরং Gold নিজে কীভাবে behave করে, যাতে Master Engine-এর rules XAUUSD-এর জন্য বাস্তবসম্মত হয়।

একটা methodological distinction আগে: নিচের market-behaviour findings-এর কিছু academic/primary-source evidence থেকে, আর session-specific trading observations-এর কিছু secondary sources থেকে। তাই আমি “proven market fact” এবং “testable hypothesis” আলাদা রাখছি।

### STEP 7G — Batch D: XAUUSD Behaviour

#### 1. প্রথম principle: XAUUSD-এর movement uniform নয়

Intraday research-এ gold-এর volatility trading day জুড়ে পরিবর্তিত হয়; historical gold-futures research-ও intraday/interday volatility variation পেয়েছে।

আর 2026-এর World Gold Council analysis-এ spot gold-এর 20-minute data ব্যবহার করে দেখা হয়েছে যে Asian এবং US trading hours-এর activity gold-এর movement-এ গুরুত্বপূর্ণ ভূমিকা রাখছে।

**অর্থাৎ আমাদের engine-এর জন্য:**

> **Time/session = contextual variable, not decoration.**

**কিন্তু এখানেই একটা correction দরকার।**

#### 2. তোমার বর্তমান Kill Zone framework-কে blindly hard-code করব না

তুমি ব্যবহার করো:

<pre><code>UTC-4 New York

ASIA          19:00-22:00
LONDON        02:00-05:00
NEW YORK      07:00-10:00
LONDON CLOSE  10:00-12:00</code></pre>

এগুলো তোমার established chart framework।

আমি এগুলো research configuration হিসেবে retain করছি।

কিন্তু research-এর evidence দেখাচ্ছে gold-এর active behaviour শুধু এই narrow windows-এ সীমাবদ্ধ নয়। London/New York overlap-এ activity গুরুত্বপূর্ণ, আর US macro events-এর সময় volatility ও execution conditions দ্রুত বদলাতে পারে।

**তাই:**

**Kill Zone ≠ mandatory HTF condition.**

এটা আমাদের আগের সিদ্ধান্তকেও reinforce করছে।

---

#### 3. Swing Engine-এর জন্য session-এর আসল role

তুমি swing trade করতে চেয়েছো।

তাই 4H/1D setup-এর জন্য:

❌ **"4H signal only valid during NY Kill Zone"**

আমি এটা চাই না।

**বরং:**

<pre><code>1W / 1D / 4H
     ↓
STRUCTURAL SETUP
     ↓
SESSION = CONTEXT
     ↓
1H / 30M
EXECUTION TIMING</code></pre>

অর্থাৎ **HTF setup session-independent হতে পারে।**

কিন্তু execution-এর সময় session behaviour গুরুত্বপূর্ণ।

এটাই তোমার swing objective-এর সঙ্গে সবচেয়ে coherent।

---

#### 4. Asia-কে আমরা কীভাবে ব্যবহার করব?

Current external evidence Asian hours-কে gold-এর price behaviour-এর গুরুত্বপূর্ণ component হিসেবে দেখাচ্ছে; WGC-এর 2026 analysis-এ Asian activity-এর সঙ্গে gold-এর support/rebound behaviour-এর সম্পর্কও দেখা গেছে।

তাই আমি আগের simplistic assumption:

> **“Asia = useless / dead session”**

**reject করছি।**

**বরং:**

**Asia = Range / Reference Context Candidate**

**যেমন:**

<pre><code>Asia High
Asia Low
   ↓
London / NY
   ↓
Does price attack one side?
   ↓
Sweep?
   ↓
Reclaim?</code></pre>

এটা আমাদের liquidity architecture-এর সঙ্গে naturally fit করে।

**তবে Asia range sweep automatically valid trade setup—এটা এখনো প্রমাণিত নয়।**

---

#### 5. London-এর role

Historical research দেখায় London এবং New York দুটোই gold price discovery-তে গুরুত্বপূর্ণ; তবে 17 বছরের intraday study-তে New York futures গড়ে larger price-discovery role দেখিয়েছে, এবং intraday variation liquidity ও macro announcements-এর সঙ্গে সম্পর্কিত ছিল।

**তাই:**

**London = potential liquidity discovery / transition phase**

**কিন্তু:**

<pre><code>London sweep
≠
automatic reversal</code></pre>

**আমাদের existing architecture:**

<pre><code>London liquidity event
           ↓
    4H/1H structure
           ↓
        CISD/MSS
           ↓
          POI</code></pre>

এর সঙ্গে ভালোভাবে fit করে।

---

#### 6. New York-কে বিশেষ গুরুত্ব দিতে হবে

এখানে evidence শক্তিশালী।

New York futures gold price discovery-তে historically significant role রাখে, এবং macroeconomic announcements-এর সঙ্গে intraday price discovery-এর variation সম্পর্কিত।

2026-এর current environment-এও US inflation, Fed expectations এবং macro data gold-এর movement-এ material impact করছে।

**তাই Master Engine-এ:**

**NY = High-impact execution regime**

**কিন্তু:**

> **High volatility = high-quality setup নয়।**

**বরং high volatility দুই জিনিস করতে পারে:**

<pre><code>A. Valid breakout accelerate
B. False sweep / slippage / violent reversal create</code></pre>

এটা আমাদের engine-এর জন্য অত্যন্ত গুরুত্বপূর্ণ।

#### 7. News Filter — এটা এখন mandatory research component

আমরা আগে news নিয়ে খুব বেশি কথা বলিনি।

এখন XAUUSD-specific research থেকে এটা বাদ দেওয়া ঠিক হবে না।

High-impact US data gold-এর intraday behaviour significantly alter করতে পারে; current trading guidance-ও CPI/NFP/FOMC-type events-এ rapid volatility এবং execution-risk-এর কথা বলছে।

**তাই final engine-এ আমি news predictor বানাতে চাই না।**

**বরং:**

<pre><code>HIGH IMPACT EVENT
        ↓
   RISK REGIME
        ↓
NORMAL / CAUTION / BLOCK</code></pre>

**Important:**

Pine Script নিজে complete economic-calendar intelligence-এর জায়গায় বসবে না।

তাই final architecture-এ **manual/session/news configuration** বা TradingView-supported event mechanism-এর feasibility আলাদাভাবে যাচাই করতে হবে।

---

#### 8. Fake Sweep বনাম Genuine Sweep

এটাই আমাদের engine-এর central problem।

আমাদের এখন পর্যন্ত architecture:

<pre><code>Liquidity Sweep
       ↓
    Reclaim
       ↓
   CISD/MSS</code></pre>

এটা good start।

**কিন্তু XAUUSD-এর high-volatility regime-এ আরও একটি distinction দরকার:**

**Type A — Reversal Sweep**

<pre><code>Liquidity taken
       ↓
 Strong reclaim
       ↓
 Delivery shift
       ↓
Opposite movement</code></pre>

**Type B — Continuation Sweep**

<pre><code>Liquidity taken
       ↓
No meaningful reclaim
       ↓
  Continuation</code></pre>

**Type C — News Expansion**

<pre><code>Liquidity taken
       ↓
Extreme volatility
       ↓
Multiple levels breached
       ↓
Normal structure temporarily unreliable</code></pre>

**তৃতীয় type-এর জন্য Trade Block / Caution regime প্রয়োজন হতে পারে।**

---

#### 9. Displacement-এর XAUUSD-specific definition এখন আরও গুরুত্বপূর্ণ

আমরা আগে বলেছিলাম:

> **“একটি বড় candle = displacement” গ্রহণ করব না।**

এখনও সেই সিদ্ধান্তই থাকছে।

আমাদের eventual detector সম্ভবত combine করবে:

<pre><code>Directional expansion
+
Structure consequence
+
Close quality
+
Relative volatility</code></pre>

**যেমন:**

<pre><code>Current impulse range
          vs
Recent 1H/30M range distribution</code></pre>

এতে fixed **$X** candle-size rule-এর dependency কমবে।

এখনও exact formula lock করছি না।

---

#### 10. Day-of-week নিয়ে interesting evidence আছে — কিন্তু rule বানাব না

Academic research-এ gold-related volatility products-এ Monday/Friday seasonality পাওয়া গেছে, কিন্তু literature-এ এই effect নিয়ে contradictory findings-ও আছে।

আর London gold-এর historical sample-এ volatility seasonality-এর pattern আলাদা ছিল।

**Professional conclusion:**

<pre><code>Monday = avoid
Friday = avoid</code></pre>

এমন arbitrary rule দেব না।

**বরং:**

**Day-of-week = research feature**

যদি backtest-এ XAUUSD-specific sample-এ statistically meaningful degradation পাওয়া যায়, তখন filter হবে।

---

#### 11. Session overlap নিয়ে final interpretation

Current sources consistently indicate London–New York overlap-এর activity/volatility গুরুত্বপূর্ণ, যদিও exact hours source/feed/DST অনুযায়ী পরিবর্তিত হয়।

কিন্তু আমাদের engine-এর জন্য আমি এটাকে:

**Execution Opportunity Window**

হিসেবে রাখছি।

**Not:**

**Mandatory Trade Window**

**অর্থাৎ:**

<pre><code>Valid 4H → 1H setup
          ↓
No London/NY overlap
          ↓
  Trade impossible ❌</code></pre>

এমন হবে না।

**বরং:**

<pre><code>Valid setup
     +
Preferred execution window
→ higher execution priority</code></pre>

**এটা অনেক বেশি flexible।**

#### 12. এখন আমাদের XAUUSD Engine-এর “No Trade” framework তৈরি হচ্ছে

এটা আমার কাছে Batch D-এর সবচেয়ে valuable output।

##### 🚫 Potential Hard Block

<pre><code>Invalid structure
OR
Setup already invalidated
OR
HTF direction conflict
OR
Contradictory structural confirmation</code></pre>

##### 🟡 Caution

<pre><code>Major macro event nearby
OR
Extreme volatility
OR
Unclear liquidity state
OR
Wide/poor execution conditions</code></pre>

##### 🟢 Normal

<pre><code>Clear HTF context
+
Liquidity event
+
Reclaim
+
CISD/MSS
+
Valid POI</code></pre>

এটা future engine-এর **regime/state machine-এর ভিত্তি** হতে পারে।

---

#### 13. Updated XAUUSD Master Engine

এখন architecture:

<pre><code>            1W
             │
      MACRO STRUCTURE
             │
             ▼
            1D
    DIRECTIONAL CONTEXT
             │
             ▼
            4H
  RANGE + LIQUIDITY EVENT
             │
             ▼
      SWEEP / RECLAIM
             │
      ┌──────┴──────┐
     CRT       Turtle Soup
      └──────┬──────┘
             │
             ▼
            1H
    DELIVERY / STRUCTURE
             │
      ┌──────┴──────┐
     CISD          MSS
      └──────┬──────┘
             │
             ▼
            SMT
         XAU ↔ XAG
             │
             ▼
       REPRICING POI
             │
      ┌──────┼──────┐
     FVG    IFVG   Breaker
      └──────┼──────┘
             │
             ▼
          UNICORN
             │
             ▼
      SESSION FILTER
             │
             ▼
        NEWS/REGIME
             │
             ▼
            30M
         EXECUTION</code></pre>

এখানে **Session** এবং **News** final directional engine নয়।

এগুলো **execution/risk regime layer**।

---

### 🔥 Batch D-এর সবচেয়ে বড় conclusion

আমাদের engine এখন আর শুধু:

> **“Signal generator”**

হওয়ার দিকে যাচ্ছে না।

বরং:

> **Context → Event → Confirmation → Validation → Regime → Execution**

এই architecture-এ যাচ্ছে।

এটাই অনেক বেশি professional।



এই ধাপের উদ্দেশ্য একটাই:

> CISD, MSS, C2, CRT Reclaim এবং Turtle Soup confirmation—এগুলো কি আলাদা edge, নাকি একই underlying market event-এর আলাদা detector?

এটা পরিষ্কার না হলে পরে আমরা একই তথ্যকে ৩–৫ বার “confluence” হিসেবে গণনা করে ফেলতে পারি।

---

### STEP 7G — B.5 Structural Confirmation Reconciliation

1. **প্রথমে source evidence**

2. তোমার Fractal source-এ sequence সরাসরি:

3. HTF level → sweep → close back → C2 → CISD → confirmation

4. এবং code-এ C2-এর পর CISD level আলাদাভাবে track করা হয়; CISD trigger হয় relevant level-এর ওপর/নিচে close-এর মাধ্যমে।

5. CRT-এর mechanics:

6. **HTF range → one-side sweep → close back inside → opposite-side delivery**। অর্থাৎ CRT-এর core confirmation হচ্ছে reclaim/close-back; পরবর্তী lower-timeframe confirmation আলাদা refinement হতে পারে।

7. MSS-এর contemporary definitions-এ liquidity event-এর পর displacement এবং relevant short-term swing break-কে structural confirmation হিসেবে ধরা হচ্ছে।

8. এখন এগুলো একসঙ্গে রাখলে picture পরিষ্কার হয়।

9. **এগুলো আলাদা edge নয়**

10. **এগুলো একই structural event-এর আলাদা-আলাদা lens/resolution**

11. **Core event একটাই:** Liquidity sweep + Invalidation of current direction + Reclaim/Displacement

### 2. একই জিনিস নয় — কিন্তু একই chain-এর অংশ

এটাই আজকের সবচেয়ে গুরুত্বপূর্ণ conclusion।

আমি এগুলোকে আর:

<pre><code>CISD = Signal #1
MSS  = Signal #2
C2   = Signal #3
CRT  = Signal #4</code></pre>

এভাবে দেখছি না।

বরং:

<pre><code>       LIQUIDITY EVENT
              │
       ┌──────┴──────┐
       │             │
     SWEEP         RANGE
       │             │
       └──────┬──────┘
              ↓
         RECLAIM / C2
              ↓
        DELIVERY SHIFT
              ↓
   MSS / CISD confirmation
              ↓
          REPRICING
              ↓
            ENTRY</code></pre>

### 3. C2-এর প্রকৃত role

Fractal source অনুযায়ী C2 তৈরি হয় যখন HTF level sweep করার পরে price সেই level-এর ভেতরে close করে। তারপর system CISD confirmation-এর অপেক্ষা করে।

**তাই:**

**C2 = Reclaim event**

এটা final entry signal নয়।

এটা বলছে:

> “Liquidity নেওয়ার পর price আবার accepted range-এর ভেতরে এসেছে।”

---

### 4. CRT-এর প্রকৃত role

CRT-ও একই জায়গায় কাজ করছে:

<pre><code>Range
  ↓
Sweep
  ↓
Close back inside</code></pre>

অর্থাৎ CRT-এর reclaim এবং Fractal-এর C2 খুব closely related।

**তাই:**

> C2 ≈ implementation label for a confirmed sweep/reclaim event

এবং

> CRT ≈ range-based framework around that event

এগুলোকে দুইটি independent confirmation হিসেবে count করা যাবে না।

**Decision:**

**CRT → Context Framework 🟡**

**C2 → Event State 🟡**


### 5. MSS বনাম CISD — এখানে আসল কাজ

এখানে subtle distinction আছে।

**MSS**

সাধারণ structural interpretation:

<pre><code>Liquidity event
       ↓
  Displacement
       ↓
Relevant swing breaks
       ↓
      MSS</code></pre>

অর্থাৎ MSS-এর focus:

> Structure changed

**CISD**

আমাদের Fractal source-এর implementation-এ CISD level opposing-candle opens থেকে derived এবং price সেই level-এর মাধ্যমে close করলে confirmation trigger হয়।

অর্থাৎ CISD-এর focus:

> Delivery changed

দুটো closely related, কিন্তু identical নয়।

### 6. তাই আমরা MSS বাদ দিচ্ছি না

বরং hierarchy করছি:

<pre><code>RECLAIM
  ↓
C2 / CRT confirmation
  ↓
DELIVERY SHIFT
  ├── CISD
  └── MSS
  ↓
CONFIRMED REVERSAL</code></pre>

এখনও প্রশ্ন:

> MSS + CISD দুটো লাগবে?

**আমার professional recommendation:**

**না—প্রথম version-এ দুটোকে mandatory AND-condition করব না।**

কারণ এতে:

<pre><code>CISD ✓
MSS  X</code></pre>

হলে ভালো setup unnecessarily reject হতে পারে।

অন্যদিকে:

<pre><code>CISD ✓
MSS  ✓</code></pre>

হলে দুটোকে আলাদা 2-point confluence হিসেবে count করাও ভুল হতে পারে।

### 7. বরং Confirmation Layer বানাই

এখন architecture:

<pre><code>       CONFIRMATION ENGINE
                │
         ┌──────┴──────┐
         │             │
       CISD           MSS
         │             │
         └──────┬──────┘
                ↓
        DELIVERY CONFIRMED</code></pre>

**তার মানে:**

**CISD এবং MSS = alternative detectors**  
একই underlying state-এর।

এটা এখন আমাদের strongest architectural hypothesis।

---

### 8. কিন্তু একটা exception আছে

যদি future testing দেখায়:

<pre><code>CISD alone
Expected value = X

MSS alone
Expected value = Y

CISD + MSS
Expected value = Z</code></pre>

এবং `Z` সত্যিই materially better হয়, তখন আমরা দুটোকে secondary confirmation hierarchy হিসেবে ব্যবহার করতে পারি।

**কিন্তু সেটা research/backtest-এর পরে।**

এখন আগে থেকে ধরে নেব না।

### 9. Turtle Soup কোথায় বসছে?

এখন Turtle Soup-কে খুব সুন্দরভাবে position করা যায়:

<pre><code>HTF Liquidity
      ↓
    Sweep
      ↓
   Reclaim
      ↓
     MSS
      ↓
  FVG / IFVG
      ↓
    Retest
      ↓
    Entry</code></pre>

**অর্থাৎ Turtle Soup:**

**একটি complete execution pathway**

**আর CISD:**

**একটি confirmation detector**

**CRT:**

**একটি range/event framework**

**Fractal:**

**একটি MTF reversal framework**

এই distinction আমাদের system massively cleaner করবে।

### 10. এখন পুরো structure নতুন করে দেখো

<pre><code>        1W / 1D
           │
     CONTEXT / BIAS
           │
           ▼
          4H
   RANGE / LIQUIDITY
           │
           ▼
    LIQUIDITY SWEEP
           │
           ▼
    RECLAIM / C2 / CRT
           │
           ▼
     DELIVERY SHIFT
           │
     ┌─────┴─────┐
     │           │
   CISD         MSS
     │           │
     └─────┬─────┘
           │
           ▼
       CONFIRMED
           │
           ▼
     REPRICING POI
     ┌─────┼─────┐
     │     │     │
    FVG   IFVG Breaker
     │     │     │
     └─────┼─────┘
           │
           ▼
        UNICORN
           │
           ▼
     SMT VALIDATION
           │
           ▼
      30M EXECUTION</code></pre>

**এখন এটা অনেক বেশি coherent।**

### 🚨 আরেকটি গুরুত্বপূর্ণ discovery

CRT-এর own documentation-এও range model-কে timeframe-nested হিসেবে দেখা হয়—higher timeframe range এবং lower timeframe execution।

**তাই আমাদের:**

**4H → 1H → 30M**

architecture arbitrary নয়।

তবে এর অর্থ এই নয় যে **4H CRT অবশ্যই প্রতিটি trade-এর জন্য mandatory**।

এটা এখনও test করতে হবে।


### STEP 7G — Batch C: XAUUSD ↔ XAGUSD SMT

#### 1. SMT-এর core definition

SMT-এর basic structure:

> একই সময়ে দুই correlated instrument-এর একটি নতুন swing high/low তৈরি করে, অন্যটি সেটি confirm করতে ব্যর্থ হলে divergence তৈরি হয়।

XAUUSD–XAGUSD-কে সাধারণত positively correlated pair হিসেবে ব্যবহার করা হয়। তবে **correlated মানেই perfectly synchronized নয়**—এটাই আমাদের জন্য গুরুত্বপূর্ণ। Gold ও Silver-এর underlying demand drivers এবং volatility আলাদা; World Gold Council-ও দুটির market behaviour-এর উল্লেখযোগ্য পার্থক্য তুলে ধরেছে।

**তাই:**

**SMT = correlation failure**

**কিন্তু**

**correlation failure ≠ automatically reversal.**
#### 2. আমাদের Master Engine-এর জন্য SMT-এর সবচেয়ে গুরুত্বপূর্ণ প্রশ্ন

ধরা যাক:

<pre><code>XAUUSD
  ↓
Previous High
  ↓
NEW HIGH / liquidity sweep</code></pre>

কিন্তু একই সময়ে:

<pre><code>XAGUSD
  ↓
Previous High
  ↓
FAILS TO MAKE NEW HIGH</code></pre>

তাহলে:

**Bearish SMT Candidate**

এটা potentially বলছে XAU-এর নতুন high broad metal-strength দ্বারা confirmed হয়নি।

**কিন্তু আমি এখানে SELL signal দিচ্ছি না।**

কারণ আমাদের architecture already বলে:

<pre><code>SMT
 ↓
WAIT
 ↓
Liquidity / Structure confirmation
 ↓
Execution</code></pre>

এটা external research-এর সঙ্গে consistent: SMT-কে confirmation/filter হিসেবে ব্যবহার করার recommendation পাওয়া যাচ্ছে, standalone entry হিসেবে নয়।

#### 3. Bullish SMT

Inverse:

<pre><code>XAU
  ↓
Previous Low
  ↓
NEW LOW / SSL sweep

XAG
  ↓
Previous Low
  ↓
HOLDS ABOVE</code></pre>

তাহলে:

**Bullish SMT Candidate**

**কিন্তু আবার:**

**SMT → candidate**

not

**SMT → BUY**

#### 4. এখানে একটা বড় সমস্যা পেলাম: “SMT” শব্দটা অনেক loosely ব্যবহৃত হয়

কিছু implementations pivot-high/pivot-low comparison ব্যবহার করে।

অন্যদিকে broader ICT explanations এটাকে key liquidity extreme-এর failure-to-confirm হিসেবে describe করে।

এই দুটো একই জিনিস নয়।

তাই আমাদের Pine Engine-এ:

❌ **“যেকোনো pivot mismatch = SMT”**

এই rule ব্যবহার করব না।

বরং আমাদের SMT detector-কে event-aware করতে হবে।

---

#### 5. Master Engine-এর জন্য আমি SMT-কে এভাবে redefine করার recommendation দিচ্ছি

<pre><code>            SMT DETECTOR
                 │
                 ▼
       Identify reference swing
                 │
                 ▼
       Is XAU attacking liquidity?
                 │
           YES   │
                 ▼
       Is XAG confirming extreme?
           /           \
         YES            NO
          │             │
        NO SMT    SMT CANDIDATE
                        │
                        ▼
                   WAIT FOR XAU
              STRUCTURAL CONFIRMATION</code></pre>

**অর্থাৎ SMT নিজে event নয়।**

**এটা liquidity event-এর cross-market validation।**

#### 6. SMT-এর সবচেয়ে গুরুত্বপূর্ণ role এখন পরিষ্কার

আমাদের architecture:

<pre><code>4H
Liquidity Sweep
  ↓
1H
Delivery Shift / CISD / MSS
  ↓
SMT
  ↓
POI
  ↓
30M Entry</code></pre>

কিন্তু আমি আরও একটি alternative test রাখছি:

<pre><code>4H
Liquidity Sweep
  ↓
SMT
  ↓
1H CISD/MSS
  ↓
POI
  ↓
30M Entry</code></pre>

**অর্থাৎ SMT confirmation-এর আগে এবং পরে—দুই অবস্থাতেই test হবে।**

আমরা এখনই কোনটা superior তা assume করব না।

#### 7. SMT-এর সবচেয়ে বড় blind spot: correlation regime

এটা খুব গুরুত্বপূর্ণ।

Gold এবং Silver একই precious-metals complex-এর অংশ হলেও তাদের behaviour এক নয়। Gold তুলনামূলকভাবে deeper/more liquid এবং Silver বেশি cyclical/high-beta behaviour দেখাতে পারে।

**তাই:**

<pre><code>Normal correlation
  ↓
SMT divergence = potentially meaningful</code></pre>

**কিন্তু:**

<pre><code>Correlation breakdown
  ↓
SMT divergence = potentially meaningless</code></pre>

এই কারণে final engine-এ SMT-এর আগে **Correlation Quality Filter** রাখার সম্ভাবনা তৈরি হয়েছে।

---

#### 8. আমি এখানে একটি গুরুত্বপূর্ণ engineering decision নিচ্ছি

**SMT mandatory হবে না।**

অর্থাৎ:

<pre><code>SMT absent
  ↓
❌ NO TRADE</code></pre>

এই rule আমি reject করছি।

কারণ SMT না থাকা মানে bearish/bullish setup invalid—এমন evidence এখন আমাদের কাছে নেই।

**বরং:**

<pre><code>VALID SETUP
  │
  ├── SMT present → QUALITY BOOST
  │
  └── SMT absent  → NORMAL</code></pre>

**কিন্তু:**

<pre><code>VALID LONG SETUP
+
Strong Bearish SMT
  ↓
REJECT / downgrade</code></pre>

এটা test করার মতো hypothesis।

**অর্থাৎ SMT-এর presence এবং contradiction-এর treatment একই হবে না।**

#### 9. SMT-কে তিন-state system বানানোর recommendation

এটা আমার current preferred design:

| SMT State | Meaning | Engine treatment |
| :--- | :--- | :--- |
| 🟢 **Aligned SMT** | Setup direction-এর সঙ্গে divergence aligned | Quality boost |
| 🟣 **No SMT** | কোনো meaningful divergence নেই | Neutral |
| 🔴 **Contradictory SMT** | Setup-এর বিপরীত divergence | Downgrade / possible reject |

**উদাহরণ:**

**আমরা LONG খুঁজছি**

<pre><code>XAU sweeps low
XAG holds low
      ↓
 Bullish SMT
      ↓
  🟢 ALIGNED</code></pre>

→ quality boost.

**কিন্তু:**

<pre><code>XAU sweeps low
XAG also confirms low
      ↓
   No SMT
      ↓
  🟣 Neutral</code></pre>

→ trade automatically rejected নয়।

**আর:**

<pre><code>XAU sweeps low
XAG makes even stronger bearish low
      ↓
Bearish/contradictory structure
      ↓
  🔴 Warning</code></pre>

→ setup downgrade/reject করার candidate।

---

#### 10. Timeframe নিয়ে গুরুত্বপূর্ণ সিদ্ধান্ত

External sources SMT-এর জন্য H1/H4 bias থেকে M5–M15 execution পর্যন্ত বিভিন্ন frameworks ব্যবহার করছে।

কিন্তু আমাদের system-এর architecture আলাদা:

**1W → 1D → 4H → 1H → 30M**

তাই অন্য trader-এর recommended timeframe copy করব না।

আমাদের research question হবে:

**HTF SMT**
4H XAU ↔ 4H XAG

ব্যবহার করে কি 1H reversal quality বাড়ে?

**Execution SMT**
1H XAU ↔ 1H XAG

ব্যবহার করে কি 30M entry quality বাড়ে?

এবং potentially:

**30M SMT**
শুধু execution refinement-এর জন্য।

---

#### 11. আমার current recommendation

আমি 4H + 1H SMT test করতে চাই।

30M SMT-কে এখনই core module করব না।

কারণ আমাদের লক্ষ্য:

> 30M-এ entry execute করা, 30M-কে পুরো decision-making engine বানানো নয়।

**তাই:**

<pre><code>1W / 1D
Context

4H
Liquidity + SMT context

1H
CISD / MSS + SMT confirmation

30M
Execution</code></pre>

**এটা অনেক cleaner।**

---

#### 12. SMT কি independent information দেয়?

এখন পর্যন্ত research-এর ভিত্তিতে:

**সম্ভাবনা: হ্যাঁ**

কারণ SMT অন্য price series থেকে information নেয়।

আমাদের primary XAU chart একা যে তথ্য দেখতে পায় না:

<pre><code>XAU event
  +
XAG response</code></pre>

SMT সেই cross-market relationship যোগ করছে।

সুতরাং এটি FVG/CISD-এর মতো একই chart-এর আরেকটি detector নয়।

**Therefore:**

**SMT is genuinely architecturally different.**

এটাই কারণ আমি এটাকে engine-এ রাখার দিকে ঝুঁকছি।

---

#### 13. কিন্তু “SMT = institutional footprint” claim আমি এখনই গ্রহণ করছি না

কিছু sources SMT-কে institutional manipulation-এর evidence হিসেবে describe করে।

কিন্তু এটাকে causal fact হিসেবে আমাদের rulebook-এ লিখব না।

আমাদের wording হবে:

> SMT is a cross-market non-confirmation condition that may improve the probability assessment of a liquidity/structure event.

**এটা scientifically অনেক cleaner।**

### 🔥 STEP 7G — Batch C-এর সবচেয়ে গুরুত্বপূর্ণ conclusion

SMT-কে আমি final engine-এ:

❌ **Standalone Signal**
হিসেবে রাখছি না।

❌ **Mandatory Condition**
হিসেও রাখছি না।

✅ **Cross-Market Validation Layer**
হিসেবে রাখছি।

**এবং:**

<pre><code>SMT PRESENT
    ↓
Quality ↑

SMT ABSENT
    ↓
Neutral

SMT CONTRADICTORY
    ↓
Quality ↓ / Reject Candidate</code></pre>

**এটাই এখন SMT Architecture Hypothesis v1।**

---

### Updated Master Engine

এখন পর্যন্ত architecture আরও mature হলো:

<pre><code>        1W
         │
   MACRO CONTEXT
         │
         ▼
        1D
 DIRECTIONAL BIAS
         │
         ▼
        4H
RANGE + LIQUIDITY EVENT
         │
         ▼
  SWEEP / RECLAIM
         │
   ┌─────┴─────┐
   │           │
  CRT     Turtle Soup
   │           │
   └─────┬─────┘
         │
         ▼
        1H
DELIVERY / STRUCTURE
         │
   ┌─────┴─────┐
   │           │
 CISD         MSS
   │           │
   └─────┬─────┘
         │
         ▼
        SMT
     XAU ↔ XAG
         │
         ▼
   REPRICING POI
   ┌─────┼─────┐
   │     │     │
  FVG   IFVG Breaker
   │     │     │
   └─────┼─────┘
         │
         ▼
      UNICORN
         │
         ▼
       30M
    EXECUTION</code></pre>


### STEP 7H — EVIDENCE RECONCILIATION MATRIX

#### 1. আমাদের final evaluation framework

প্রতিটি concept-কে ৬টি প্রশ্নে বিচার করছি:

1. **Unique information দেয়?**
2. **অন্য concept-এর সঙ্গে duplicate কি না?**
3. **XAUUSD-এর জন্য logically relevant?**
4. **কোন timeframe-এ সবচেয়ে natural?**
5. **Directional signal, confirmation, POI, filter—কোন role?**
6. **Backtest ছাড়া rule lock করা নিরাপদ কি না?**

---

#### 2. MASTER MATRIX — Version 0.1

| Concept | Primary Role | Recommended TF | Decision | Reason |
| :--- | :--- | :---: | :---: | :--- |
| **1W Structure** | Macro Context | 1W | 🟢 KEEP | Long-horizon structural context |
| **1D Structure** | Directional Context | 1D | 🟢 KEEP | Swing bias-এর প্রধান context |
| **Liquidity** | Market Event | 4H/1H | 🟢 CORE | বহু source-এর recurring primitive |
| **Liquidity Sweep** | Trigger Event | 4H/1H | 🟢 CORE | Reversal/continuation distinction-এর ভিত্তি |
| **CRT** | Range Framework | 4H | 🟢 KEEP / MERGE | Sweep + reclaim context |
| **C2** | Reclaim State | 4H/1H | 🟡 MERGE CANDIDATE | CRT-এর reclaim-এর সঙ্গে overlap |
| **Turtle Soup** | Reversal Model | 4H→1H | 🟢 KEEP | Complete sweep/reversal pathway |
| **CISD** | Delivery Confirmation | 1H | 🟢 CORE | Delivery shift detector |
| **MSS** | Structural Confirmation | 1H | 🟡 ALTERNATIVE | CISD-এর সঙ্গে overlap test required |
| **FVG** | Repricing POI | 1H/30M | 🟢 KEEP | Entry location |
| **IFVG** | Inversion POI | 1H/30M | 🟢 KEEP | Failed FVG state |
| **Breaker** | Repricing POI | 1H/30M | 🟢 KEEP | Structural POI |
| **Unicorn** | Composite POI | 1H/30M | 🟢 KEEP CANDIDATE | FVG + Breaker combination |
| **Fractal Model** | MTF Framework | 4H→1H | 🟡 MERGE | Architecture rather than separate signal |
| **SMT** | Cross-market Validation | 4H/1H | 🟢 KEEP | Independent XAG information |
| **Session** | Execution Regime | 1H/30M | 🟢 KEEP | Timing/context |
| **News Regime** | Risk Filter | 1H/30M | 🟡 KEEP | Potentially important, implementation constraint |
| **Double Purge** | Invalidation Logic | 4H/1H | 🟡 TEST | Interesting but needs evidence |
| **Inner Sweep** | Entry Refinement | 30M | 🟡 TEST | Potentially valuable execution trigger |
| **Displacement** | Confirmation Component | 1H/30M | 🟢 KEEP | Needed to distinguish meaningful shift |
| **Day-of-week** | Statistical Filter | — | 🟡 TEST | No hard rule yet |
| **Kill Zone** | Timing Preference | 1H/30M | 🟢 KEEP | Preference, not HTF requirement |

#### 3. এখন সবচেয়ে গুরুত্বপূর্ণ MERGE

আমাদের final engine-এ আমি চাই না:

<pre><code>CRT  ✓
C2  ✓
Turtle Soup  ✓
Liquidity Sweep  ✓</code></pre>

সবগুলোকে চারটি independent score দেওয়া হোক।

এটা double/triple counting তৈরি করবে।

**বরং:**

<pre><code>         LIQUIDITY EVENT
                │
              SWEEP
                │
         ┌──────┴──────┐
        CRT       Turtle Soup
         └──────┬──────┘
                │
                ▼
            RECLAIM/C2</code></pre>

**Architectural interpretation:**

**Liquidity Sweep = primitive**

**CRT = framework**

**Turtle Soup = setup model**

**C2 = state/event**

এগুলো আলাদা layer।

---

#### 4. CISD বনাম MSS

এখানে final decision এখনো:

**❌ Merge completely**  
করছি না।

**❌ দুটো mandatory**  
করছি না।

**বরং:**

<pre><code>       DELIVERY / STRUCTURE SHIFT
                   │
            ┌──────┴──────┐
           CISD          MSS
            └──────┬──────┘
                   │
                   ▼
              CONFIRMATION</code></pre>

**Current rule:**

> **CISD এবং MSS = competing/alternative confirmation detectors.**

**Backtest-এ দেখা হবে:**

* **CISD alone**
* **MSS alone**
* **CISD + MSS**
* **কোনটি earliest?**
* **কোনটি false-positive কমায়?**
* **কোনটি XAUUSD-এর জন্য বেশি robust?**

**এই test না হওয়া পর্যন্ত দুটোকে একই score দেওয়া হবে না।**

---

#### 5. FVG / IFVG / Breaker / Unicorn

এখানে architecture আরও পরিষ্কার।

এগুলো direction generator নয়।

**বরং:**

<pre><code>Direction
    ↓
Liquidity Event
    ↓
Confirmation
    ↓
   POI
   ├─ FVG
   ├─ IFVG
   ├─ Breaker
   └─ Unicorn</code></pre>

**অর্থাৎ:**

**FVG = POI**

**IFVG = POI state/inversion**

**Breaker = structural POI**

**Unicorn = composite POI**

**এগুলোকে একসঙ্গে “four confirmations” বানানো হবে না।**

---

#### 6. Unicorn-এর ক্ষেত্রে একটা সতর্কতা

Unicorn visually খুব attractive কারণ:

<pre><code>Breaker
+
FVG
=
Unicorn</code></pre>

কিন্তু এখানেই danger:

যদি engine বলে:

<pre><code>FVG  ✓
Breaker  ✓
Unicorn  ✓</code></pre>

তাহলে একই underlying condition তিনবার score করা হবে।

**তাই final architecture:**

**Unicorn = composite classification**

not:

**Unicorn = additional confirmation point**

**এটা খুব গুরুত্বপূর্ণ।**

---

#### 7. SMT-এর final provisional position

আমাদের আগের research decision এখানে unchanged:

<pre><code>Primary Engine
      ↓
 Valid setup
      ↓
    SMT
   ┌─┼─┐
   ↓ ↓ ↓
   + 0 -</code></pre>

**অর্থাৎ:**

🟢 aligned SMT → quality boost

🟣 no SMT → neutral

🔴 contradictory SMT → downgrade/reject candidate

**কিন্তু:**

**SMT setup তৈরি করবে না।**

**এটা validation layer।**

---

#### 8. Fractal Model-এর role পরিবর্তন

Fractal Model-কে আলাদা signal engine বানানো আমি এখন recommend করছি না।

বরং এর সবচেয়ে valuable contribution:

> **HTF → LTF state propagation**

**অর্থাৎ:**

<pre><code>  4H liquidity event
          ↓
1H structural state
          ↓
30M execution state</code></pre>

এই architecture-এ Fractal-এর concept ব্যবহার করা যেতে পারে, কিন্তু তার সব individual signal blindly copy করা হবে না।

**Decision:**

**Fractal = Architecture inspiration / MTF state framework**

🟡 **MERGE**

---

#### 9. সবচেয়ে গুরুত্বপূর্ণ নতুন architecture

এখন আমরা পুরো system-কে ৭টি layer-এ নামিয়ে আনতে পারি:

<pre><code>┌───────────────────────────────┐
│ LAYER 1 ── MACRO CONTEXT      │
│         1W → 1D               │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 2 ── LIQUIDITY          │
│         4H                    │
│ Range / Sweep / Reclaim       │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 3 ── STRUCTURE          │
│         1H                    │
│ CISD / MSS / Displacement     │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 4 ── CROSS-MARKET       │
│         XAU ↔ XAG             │
│            SMT                │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 5 ── POI                │
│ FVG / IFVG / Breaker /        │
│ Unicorn                       │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 6 ── REGIME             │
│ Session / News / Volatility   │
└───────────────┬───────────────┘
                │
                ▼
┌───────────────────────────────┐
│ LAYER 7 ── EXECUTION          │
│         30M                   │
│ Entry / SL / TP / Mgmt        │
└───────────────────────────────┘</code></pre>

**এখন এটাই আমাদের Master Engine-এর architectural backbone হিসেবে সবচেয়ে শক্তিশালী candidate।**

#### 10. একটি গুরুত্বপূর্ণ correction

আগের architecture-এ আমরা কিছু জায়গায় SMT-কে confirmation-এর পরে রেখেছিলাম।

এখন আমি সেটাকে fixed position হিসেবে lock করছি না।

কারণ বাস্তবে SMT দুইভাবে test করা দরকার:

**Model A**

<pre><code>Sweep
  ↓
SMT
  ↓
CISD/MSS
  ↓
POI
  ↓
30M</code></pre>

**Model B**

<pre><code>Sweep
  ↓
CISD/MSS
  ↓
SMT
  ↓
POI
  ↓
30M</code></pre>

**Backtest না হওয়া পর্যন্ত কোনটি superior তা বলা অতিরিক্ত confidence হবে।**

---

#### 11. Final Signal Architecture — এখনো coding নয়

আমাদের engine ideally এমন হবে:

<pre><code>             1W
              │
        Macro Context
              │
              ▼
             1D
      Directional Bias
              │
              ▼
             4H
      Liquidity / Range Event
              │
              ▼
         Sweep/Reclaim
              │
              ▼
      Setup Qualification
              │
              ▼
             1H
              │
              ▼
   CISD / MSS + Displacement
              │
              ▼
        SMT Validation
              │
              ▼
             POI
     ┌────────┼────────┐
     ↓        ↓        ↓
    FVG      IFVG   Breaker
              │
           Unicorn
              │
              ▼
        Regime Filter
              │
              ▼
             30M
              │
              ▼
           EXECUTE</code></pre>

---

#### 12. এখন আমাদের সবচেয়ে গুরুত্বপূর্ণ “Anti-Bias” Rule

আমি চাই না final indicator:

> **“১০টা concept আছে → ৮টা green → BUY”**

এই ধরনের scoring machine হয়ে যাক।

কারণ ১০টি concept-এর মধ্যে ৫টি যদি একই underlying event-এর derivative হয়, তাহলে ৮/১০ আসলে ৮টি independent evidence নয়।

**তাই final engine হবে:**

> **Evidence hierarchy, not indicator counting.**

---

#### 13. Decision Hierarchy

আমি বর্তমানে এই hierarchy recommend করছি:

##### Tier 1 — Must-have

<pre><code>HTF Context
+
Liquidity Event
+
Valid Structural Confirmation</code></pre>

##### Tier 2 — Quality

<pre><code>SMT
+
Displacement Quality
+
POI Quality</code></pre>

##### Tier 3 — Execution

<pre><code>Session
+
30M confirmation
+
Risk/News regime</code></pre>

##### Tier 4 — Optional enhancement

<pre><code>CRT classification
Turtle Soup classification
Unicorn classification
Inner Sweep
Double Purge</code></pre>

**এগুলো core logic-এর উপর বসবে; core logic replace করবে না।**

---

#### 14. KEEP / MERGE / MODIFY / TEST / DROP

🟢 **KEEP — Core**

* Liquidity
* Liquidity Sweep
* 1W/1D context
* CISD
* Displacement
* FVG
* IFVG
* Breaker
* SMT
* Session/regime framework

🟡 **MERGE**

* CRT + C2
* Fractal MTF logic
* Unicorn with Breaker/FVG

🟡 **MODIFY**

* MSS
* Turtle Soup
* Kill Zone
* News filter

🟡 **TEST**

* Inner Sweep
* Double Purge
* Day-of-week
* 30M SMT
* CISD vs MSS superiority
* CRT vs Turtle Soup superiority

🔴 **DROP FOR NOW**

**আমি এখনো কোনো major concept permanently DROP করছি না।**

কারণ source-based research থেকে “concept useless” বলা এবং backtest-এ “concept has no incremental edge” প্রমাণ করা এক জিনিস নয়।

### STEP 7I — SYSTEM SYNTHESIS

#### 1. প্রথমে Master Engine-এর fundamental philosophy

আমাদের engine-এর কাজ হবে না:

> **“চার্টে যত বেশি ICT concept পাওয়া যায়, তত বেশি signal দেওয়া।”**

বরং:

> **Market context → liquidity event → structural confirmation → location → validation → execution**

অর্থাৎ প্রতিটি layer-এর আলাদা দায়িত্ব থাকবে।

---

### 2. Complete Pipeline

<pre><code>
1W
 │
 │ Macro Structure
 ▼
1D
 │
 │ Directional Context
 ▼
4H
 │
 │ Liquidity / Range Event
 ▼
Sweep
 │
 │ Reclaim
 ▼
4H/1H Setup State
 │
 ▼
1H
 │
 │ CISD / MSS + Displacement
 ▼
Structural Confirmation
 │
 ▼
SMT
 │
 │ Cross-market validation
 ▼
POI
 │
 ├── FVG
 ├── IFVG
 ├── Breaker
 └── Unicorn
 │
 ▼
Regime
 │
 ├── Session
 ├── Volatility
 └── News Risk
 │
 ▼
30M
 │
 │ Execution Confirmation
 ▼
ENTRY
</code></pre>

এখন প্রতিটি transition-এর Input → Condition → State → Output নির্ধারণ করি।

---

### 3. LAYER 1 — 1W MACRO CONTEXT

**Input**

* Weekly price structure
* Major swing high/low
* Current range position

**উদ্দেশ্য**

1W সরাসরি entry signal দেবে না।

এর কাজ:

> **Market-এর long-horizon structural environment নির্ধারণ করা।**

**Output**

<pre><code>WEEKLY_CONTEXT =
    BULLISH
    BEARISH
    NEUTRAL</code></pre>

**Important**

**NEUTRAL = automatic short/long নয়।**

এটা শুধু বলে:

> **“Weekly structure থেকে clear directional advantage পাওয়া যাচ্ছে না।”**

#### 4. LAYER 2 — 1D DIRECTIONAL CONTEXT

1D হবে আমাদের swing-engine-এর প্রধান contextual layer।

**Input**

* Daily structure
* Daily liquidity
* Daily range position
* 1W context

**Output**

<pre><code>DAILY_BIAS =
    LONG
    SHORT
    NEUTRAL</code></pre>

**Dependency**

<pre><code>1W Context
    ↓
1D Interpretation</code></pre>

কিন্তু 1W এবং 1D conflict হলে আমরা সরাসরি trade reject করব না।

**বরং:**

<pre><code>1W bullish
1D bearish
    ↓
TRANSITION / COUNTERTREND STATE</code></pre>

এটা আলাদা state হতে পারে।

---

#### 5. LAYER 3 — 4H LIQUIDITY ENGINE

এটা Master Engine-এর প্রথম event-detection layer।

**আমরা খুঁজব:**

* External liquidity
* Internal liquidity
* Previous highs/lows
* Range extremes
* Relevant swing points
* Potential liquidity pools

**তারপর:**

<pre><code>LIQUIDITY LEVEL
       ↓
 PRICE ATTACK
       ↓
    SWEEP?</code></pre>

---

#### 6. Sweep-এর definition

শুধু wick level cross করলেই:

> ❌ **“Valid Sweep”**

বলব না।

**আমাদের state model:**

<pre><code>LEVEL IDENTIFIED
       ↓
 LEVEL ATTACKED
       ↓
 SWEEP DETECTED
       ↓
    RECLAIM?</code></pre>

অর্থাৎ sweep এবং confirmation আলাদা।

---

#### 7. LAYER 4 — RECLAIM / CRT / C2

এখানে CRT এবং C2-এর information আসবে।

<pre><code>Sweep
  ↓
Close back / reclaim
  ↓
Reclaim confirmed</code></pre>

এখানে আমরা:

`RECLAIM_CONFIRMED = TRUE`

করতে পারি।

**কিন্তু:**

> **Reclaim confirmed ≠ entry**

এটা শুধু setup state এগিয়ে দেয়।

---

#### 8. Setup State Machine

এখন আমাদের engine-এর সবচেয়ে গুরুত্বপূর্ণ engineering abstraction তৈরি হচ্ছে:

<pre><code>STATE 0
NO SETUP
  ↓
STATE 1
CONTEXT VALID
  ↓
STATE 2
LIQUIDITY IDENTIFIED
  ↓
STATE 3
SWEEP DETECTED
  ↓
STATE 4
RECLAIM CONFIRMED
  ↓
STATE 5
STRUCTURAL SHIFT
  ↓
STATE 6
POI IDENTIFIED
  ↓
STATE 7
EXECUTION READY
  ↓
STATE 8
ENTRY</code></pre>

এটা আমাদের indicator-কে static pattern detector-এর বদলে **event-driven engine** বানাবে।

---

#### 9. LAYER 5 — 1H STRUCTURAL CONFIRMATION

এখানে:

**CISD**

এবং

**MSS**

দুটো detector থাকবে।

**কিন্তু এখনকার architecture:**

<pre><code>       STRUCTURAL SHIFT
               │
        ┌──────┴──────┐
       CISD          MSS
        └──────┬──────┘
               │
               ▼
          CONFIRMATION</code></pre>

**Current rule**

একটি valid confirmation-এর জন্য:

<pre><code>CISD
 OR
MSS</code></pre>

প্রথম version-এ `AND` নয়।

---

#### 10. Displacement এখানে কী করবে?

CISD/MSS alone যথেষ্ট নাও হতে পারে।

কারণ microscopic structural break noise হতে পারে।

**তাই:**

<pre><code>   Structural Shift
          +
Meaningful Displacement
          ↓
HIGHER QUALITY CONFIRMATION</code></pre>

এখানে “meaningful”-এর exact mathematical definition এখনো lock করিনি।

এটা পরের Rulebook-এর অন্যতম গুরুত্বপূর্ণ parameter হবে।

#### 11. LAYER 6 — SMT

এখন structural confirmation-এর পরে cross-market validation।

<pre><code>XAUUSD
  ↕
XAGUSD</code></pre>

**তিনটি state:**

<pre><code>SMT = ALIGNED
SMT = NEUTRAL
SMT = CONTRADICTORY</code></pre>

**Engine treatment:**

<pre><code>ALIGNED
  ↓
Quality Boost

NEUTRAL
  ↓
No Change

CONTRADICTORY
  ↓
Quality Downgrade / Reject Candidate</code></pre>

**কোন threshold-এ downgrade হবে—এখনো backtest-dependent।**

---

#### 12. LAYER 7 — POI ENGINE

Structural confirmation-এর পরে আমরা location চাই।

এখানে:

<pre><code>FVG
IFVG
Breaker
Unicorn</code></pre>

থাকবে।

কিন্তু সব একসঙ্গে mandatory নয়।

---

#### 13. POI hierarchy

আমি provisional hierarchy এভাবে রাখছি:

**Level 1 — Basic POI**

<pre><code>FVG
IFVG
Breaker</code></pre>

**Level 2 — Composite POI**

<pre><code>Unicorn</code></pre>

**অর্থাৎ:**

> **Unicorn আলাদা fourth signal নয়।**

এটা existing POI components-এর **higher-quality classification**।

---

#### 14. POI validity

একটা FVG তৈরি হলেই:

<pre><code>FVG = VALID ENTRY</code></pre>

হবে না।

আমাদের eventual POI state হবে:

<pre><code>CREATED
  ↓
ACTIVE
  ↓
TESTED
  ↓
RESPECTED</code></pre>

অথবা:

<pre><code>CREATED
  ↓
INVALIDATED</code></pre>

এখানে IFVG-এর concept বিশেষভাবে useful।

---

#### 15. LAYER 8 — REGIME ENGINE

এখানে তিনটি প্রধান variable:

<pre><code>SESSION
VOLATILITY
NEWS RISK</code></pre>

**Session**

তোমার preferred framework:

<pre><code>Asia            19-22
London          02-05
NY              07-10
London Close    10-12</code></pre>

এগুলো আমরা configuration, not hardcoded truth হিসেবে রাখব।

---

#### 16. Session-এর role

আমি final architecture-এ:

<pre><code>SESSION = ENTRY PRIORITY</code></pre>

রাখছি।

না যে:

<pre><code>SESSION = SETUP VALIDITY</code></pre>

অর্থাৎ valid 4H/1H setup Kill Zone-এর বাইরে তৈরি হতে পারে।

কিন্তু 30M execution-এর সময় preferred session থাকলে:

> **execution quality score বাড়তে পারে।**

---

#### 17. Volatility Regime

এখন তিনটি provisional state:

<pre><code>NORMAL
ELEVATED
EXTREME</code></pre>

**NORMAL**

Normal execution conditions.

**ELEVATED**

Caution.

**EXTREME**

Potential trade block.

বিশেষ করে XAUUSD-এর violent expansion-এর সময়।

---

#### 18. News Regime

এখানেও:

<pre><code>NORMAL
CAUTION
BLOCK</code></pre>

কিন্তু এখানে Pine implementation feasibility পরে পরীক্ষা করতে হবে।

আমরা এমন কোনো fake “news detector” বানাব না যা আসলে reliable economic calendar data পাচ্ছে না।

#### 19. LAYER 9 — 30M EXECUTION

এখন আমরা আসল execution timeframe-এ পৌঁছালাম।

30M-এর কাজ:

> **HTF/1H thesis-এর execution confirmation দেওয়া।**

30M নতুন directional thesis তৈরি করবে না।

---

#### 20. 30M Entry Candidate

Long example:

<pre><code>1D Bias = Bullish
  ↓
4H Sell-side liquidity swept
  ↓
Reclaim confirmed
  ↓
1H CISD/MSS bullish
  ↓
POI identified
  ↓
SMT not contradictory
  ↓
30M execution condition
  ↓
ENTRY CANDIDATE</code></pre>

এখানে এখনো trade নেওয়া হয়নি।

এটা:

`EXECUTION_CANDIDATE`

---

#### 21. Final Entry Gate

শেষ gate:

<pre><code>CONTEXT ✓
LIQUIDITY ✓
RECLAIM ✓
STRUCTURE ✓
POI ✓
SMT ✓/neutral
REGIME ✓
30M EXECUTION ✓
  ↓
ENTRY</code></pre>

যদি কোনো mandatory condition fail করে:

<pre><code>NO ENTRY</code></pre>

টাই আমাদের anti-overtrading architecture।

---

#### 22. Short-side mirror

Short-এর জন্য পুরো system mirror হবে:

<pre><code>1D Bearish
  ↓
4H Buy-side sweep
  ↓
Reclaim
  ↓
1H bearish CISD/MSS
  ↓
Bearish displacement
  ↓
Bearish POI
  ↓
SMT aligned/neutral
  ↓
30M execution
  ↓
SHORT</code></pre>

---

#### 23. এখন সবচেয়ে গুরুত্বপূর্ণ: INVALIDATION

Professional engine-এর জন্য entry condition-এর মতো invalidation equally important।

আমাদের state machine-এ প্রতিটি setup-এর:

<pre><code>ACTIVE
INVALIDATED
EXPIRED
TRIGGERED</code></pre>

state থাকবে।

**উদাহরণ**

<pre><code>Sweep detected
  ↓
Reclaim
  ↓
Wait for confirmation
  ↓
Price invalidates sweep structure
  ↓
SETUP = INVALID</code></pre>

পুরনো signal chart-এ পড়ে থাকবে না।

---

#### 24. Setup Expiry

আরেকটি critical rule:

> **Setup forever valid থাকবে না।**

**উদাহরণ:**

<pre><code>Sweep
  ↓
Reclaim
  ↓
No structural confirmation
  ↓
X candles pass
  ↓
EXPIRED</code></pre>

Exact candle expiry এখন parameter হিসেবে রাখব।

---

#### 25. এখন আমরা একটি “Master Signal” কী তা define করতে পারি

একটি signal তখনই তৈরি হবে যখন:

<pre><code>HTF Context
+
Liquidity Event
+
Structural Confirmation
+
Valid POI
+
Execution Condition</code></pre>

এগুলো satisfy করে।

SMT/session/news:

**quality/risk modifiers।**

এটা গুরুত্বপূর্ণ কারণ signal এবং confidence একই জিনিস নয়।

---

#### 26. Signal ≠ Score

আমি final indicator-এ এই ভুলটা করতে চাই না:

<pre><code>CISD +1
MSS +1
FVG +1
IFVG +1
Breaker +1
Unicorn +1
SMT +1
CRT +1</code></pre>

তারপর:

> **7/8 = BUY**

এটা conceptually দুর্বল।

কারণ:

**Unicorn already contains FVG + Breaker.**

এবং CRT/C2/Sweep-ও related।

---

#### 27. বরং আমরা দুইটি output তৈরি করব

**A. Directional State**

<pre><code>LONG
SHORT
NEUTRAL</code></pre>

**B. Setup Quality**

<pre><code>A+
A
B
C
INVALID</code></pre>

এগুলো আলাদা।

---

#### 29. এই architecture-এর সবচেয়ে বড় advantage

এতে indicator তিনটি আলাদা প্রশ্নের উত্তর দেবে:

**Question 1**

**Where are we?**

→ 1W / 1D

**Question 2**

**What happened?**

→ Liquidity / Sweep / Reclaim / Structure

**Question 3**

**Can I execute?**

→ POI / SMT / Regime / 30M

**এই separation-টাই আমাদের system-এর backbone।**

#### STEP 7J — XAUUSD MASTER ENGINE

#### MASTER ENGINE RULEBOOK v1.0

**System Objective**

**Primary Market:** XAUUSD  
**Execution TF:** 30M  
**Decision TF:** 1H / 4H  
**Context TF:** 1D / 1W  
**Secondary Market:** XAGUSD for SMT  
**Primary objective:** Swing-context থেকে high-quality 30M execution candidate তৈরি করা।

---

#### 1. SYSTEM ARCHITECTURE

<pre><code>                ┌───────────────┐
                │      1W       │
                │ Macro Context │
                └───────┬───────┘
                        ↓
                ┌───────────────┐
                │      1D       │
                │ Daily Context │
                └───────┬───────┘
                        ↓
                ┌───────────────┐
                │      4H       │
                │ Liquidity     │
                │ + Range Event │
                └───────┬───────┘
                        ↓
                 SWEEP / RECLAIM
                        ↓
                ┌───────────────┐
                │      1H       │
                │ CISD / MSS    │
                │ Displacement  │
                └───────┬───────┘
                        ↓
                       SMT
                        ↓
                ┌───────────────┐
                │     POI       │
                │ FVG / IFVG    │
                │ Breaker       │
                │ Unicorn       │
                └───────┬───────┘
                        ↓
                REGIME FILTER
                        ↓
                ┌───────────────┐
                │      30M      │
                │  Execution    │
                └───────┬───────┘
                        ↓
                      ENTRY</code></pre>

#### 2. STATE MACHINE

এটাই Pine implementation-এর backbone হবে।

<pre><code>S0 = NO_SETUP
  ↓
S1 = CONTEXT_VALID
  ↓
S2 = LIQUIDITY_IDENTIFIED
  ↓
S3 = SWEEP_DETECTED
  ↓
S4 = RECLAIM_CONFIRMED
  ↓
S5 = STRUCTURE_CONFIRMED
  ↓
S6 = POI_ACTIVE
  ↓
S7 = EXECUTION_READY
  ↓
S8 = ENTRY_TRIGGERED</code></pre>

এবং যেকোনো সময়:

<pre><code>INVALIDATED
EXPIRED</code></pre>

state-এ যেতে পারবে।

**অত্যন্ত গুরুত্বপূর্ণ:**

একটি candle-এ পুরো chain complete হয়ে গেলেও engine-কে historical hindsight দিয়ে সব state একসঙ্গে দেখানো যাবে না।

প্রতিটি state sequentially confirm করতে হবে।

এটা repaint prevention-এর জন্য fundamental।

---

#### 3. RULE GROUP — CTX

**CTX-01 — Weekly Context**

**TF:** 1W  
**Output:**

<pre><code>W_BULLISH
W_BEARISH
W_NEUTRAL</code></pre>

**Role**

Macro context only.

❌ **Entry trigger নয়।**

---

**CTX-02 — Daily Context**

**TF:** 1D  
**Output:**

<pre><code>D_BULLISH
D_BEARISH
D_NEUTRAL</code></pre>

**1W-এর সঙ্গে relationship:**

<pre><code>1W Bullish + 1D Bullish
→ aligned

1W Bullish + 1D Bearish
→ transition/countertrend

1W Bearish + 1D Bearish
→ aligned

1W Bearish + 1D Bullish
→ transition/countertrend</code></pre>

**Professional decision:**

1W/1D conflict = automatic no-trade নয়।

কিন্তু setup quality downgrade candidate।

---

#### 4. RULE GROUP — LIQ

**LIQ-01 — Qualified Liquidity**

4H/1H-এ relevant liquidity level identify করতে হবে।

**Candidate:**

<pre><code>Previous Swing High
Previous Swing Low
External Range High
External Range Low
Relevant Internal Liquidity</code></pre>

**কিন্তু:**

প্রতিটি minor pivot liquidity হিসেবে ব্যবহার করা যাবে না।

এখানে swing qualification algorithm প্রয়োজন হবে।

Exact algorithm v1.0-এর পরের engineering specification-এ নির্ধারণ করব।

---

#### 5. LIQ-02 — Sweep Detection

<pre><code>Qualified Liquidity
  ↓
Price breaches level
  ↓
SWEEP_DETECTED</code></pre>

**কিন্তু:**

> **Sweep alone = signal নয়।**

#### 6. LIQ-03 — Sweep Direction

**Sell-side liquidity swept:**

<pre><code>Low breached
→ potential bullish reversal</code></pre>

**Buy-side liquidity swept:**

<pre><code>High breached
→ potential bearish reversal</code></pre>

এগুলো candidate directional hypothesis।

Final direction নয়।

---

#### 7. LIQ-04 — Sweep Failure

যদি expected reclaim না আসে এবং price sweep direction-এ continue করে:

<pre><code>SWEEP
  ↓
NO_RECLAIM
  ↓
CONTINUATION_RISK</code></pre>

Setup candidate বাতিল হতে পারে।

---

#### 8. RULE GROUP — RECLAIM

**REC-01**

Sweep-এর পরে price relevant level/range-এর ভেতরে close-back করলে:

<pre><code>RECLAIM_CONFIRMED = TRUE</code></pre>

এটাই CRT/C2 family-এর event-state layer।

**গুরুত্বপূর্ণ:**

<pre><code>RECLAIM ≠ ENTRY</code></pre>

---

#### 9. REC-02 — CRT

CRT-কে standalone signal হিসেবে score করব না।

এর role:

> **Range + sweep + reclaim framework**

অর্থাৎ:

<pre><code>CRT_VALID</code></pre>

একটি contextual classification হতে পারে।

---

#### 10. REC-03 — C2

C2-কে:

> **Reclaim state**

হিসেবে treat করব।

তাই:

<pre><code>CRT ✓
C2 ✓</code></pre>

মানে দুই independent confirmations নয়।

---

#### 11. RULE GROUP — STRUCTURE

**STR-01 — Structural Confirmation**

1H-এ:

<pre><code>CISD OR MSS</code></pre>

এর মাধ্যমে structural shift detect হবে।

**v1.0 principle:**

<pre><code>CISD = Detector A
MSS  = Detector B</code></pre>

দুটো একসঙ্গে mandatory নয়।

---

#### 12. STR-02 — CISD

CISD source implementation-এর terminology/logic preserve করা হবে।

এখানে গুরুত্বপূর্ণ:

**আমরা source-এর CISD logic rewrite করে generic BOS/MSS বানাব না।**

Pine implementation-এর সময় source code থেকে exact mechanics preserve/translate করতে হবে।

---

#### 13. STR-03 — MSS

MSS structural-shift detector হিসেবে থাকবে।

কিন্তু:

<pre><code>MSS ≠ automatic entry</code></pre>

বরং:

<pre><code>MSS
+
Displacement</code></pre>

একটি stronger structural confirmation candidate।

---

#### 14. STR-04 — CISD + MSS

**Initial implementation:**

<pre><code>CISD OR MSS</code></pre>

**Advanced testing:**

<pre><code>CISD only
MSS only
CISD + MSS</code></pre>

Backtest determine করবে কোন configuration robust।

---

#### 15. STR-05 — Displacement

Displacement-এর উদ্দেশ্য:

> **Minor/noisy structure break এবং meaningful directional delivery আলাদা করা।**

তাই:

<pre><code>Structure Shift
+
Meaningful Displacement
  ↓
Higher-quality confirmation</code></pre>

**Exact displacement threshold:**

**NOT LOCKED YET.**

কারণ fixed candle size XAUUSD-এর different volatility regime-এ দুর্বল হতে পারে।

---

#### 16. RULE GROUP — SMT

**SMT-01**

**Secondary market:**  
XAGUSD

**Primary:**  
XAUUSD

SMT detect করবে:

<pre><code>XAU extreme
vs
XAG confirmation/failure</code></pre>

---

#### 17. SMT-02 — Three-State Model

<pre><code>SMT_ALIGNED
SMT_NEUTRAL
SMT_CONTRADICTORY</code></pre>

**ALIGNED**

Setup direction-এর সঙ্গে SMT supportive।

**NEUTRAL**

Meaningful SMT নেই।

**CONTRADICTORY**

Cross-market behaviour setup-এর বিপরীত।

## 18. SMT-03 — SMT Treatment

❌ Mandatory নয়

```
No SMT
≠
No Trade
```

🟢 **Aligned**

Quality enhancement।

⚪ **Neutral**

No modification।

🔴 **Contradictory**

Quality downgrade / possible rejection।

---

## 19. SMT-04 — Timeframes

Initial testing:

```
4H SMT
1H SMT
```

30M SMT:

```
Experimental
```

কারণ 30M-এর কাজ execution, primary thesis generation নয়।

---

## 20. RULE GROUP — POI

### POI-01

Valid structural confirmation-এর পরে POI খোঁজা হবে।

Candidate:

```
FVG
IFVG
Breaker
Unicorn
```

---

## 21. POI-02 — FVG

FVG = potential repricing location।

❌ FVG alone = trade signal নয়।

Required upstream context:

```
Context
+
Liquidity Event
+
Structure
```

---

## 22. POI-03 — IFVG

IFVG-কে:

> Inversion / failed imbalance state

হিসেবে treat করা হবে।

এটি FVG-এর duplicate signal নয়।

---

## 23. POI-04 — Breaker

Breaker = structural POI candidate।

এটি directional thesis তৈরি করবে না।

---

## 24. POI-05 — Unicorn

Unicorn:

```
Breaker
+
FVG
```

composite POI classification হিসেবে থাকবে।

❌ এভাবে নয়:

```
FVG +1
Breaker +1
Unicorn +1
```

কারণ এতে double-counting হবে।

---

## 25. RULE GROUP — TURTLE SOUP

Turtle Soup-কে আমরা complete setup pathway হিসেবে রাখছি।

Conceptual chain:

```
Liquidity
↓
External Sweep
↓
Rejection / Close Back
↓
MSS
↓
FVG / IFVG Confluence
↓
Retest / Inner Sweep
↓
Entry
```

এখানে একটি critical architectural decision:

Turtle Soup-এর প্রতিটি component আলাদা signal হিসেবে count হবে না।

বরং:

```
TURTLE_SOUP_SETUP = TRUE
```

একটি setup classification হবে।

---

## 26. Turtle Soup + Master Engine

এখন engine-এ দুইটি pathway থাকতে পারে:

**Generic pathway**

```
Sweep
→ Reclaim
→ CISD/MSS
→ POI
→ 30M
```

**Turtle Soup pathway**

```
Sweep
→ Reclaim
→ MSS
→ FVG/IFVG
→ Retest/Inner Sweep
→ 30M
```

অর্থাৎ Turtle Soup generic engine-কে replace করবে না।

এটা একটি specialized route।

---

## 27. Double Purge

Current status:

```
DOUBLE_PURGE = OPTIONAL / TEST
```

যদি second breach setup invalidates করে:

```
Sweep
↓
Reclaim
↓
Second breach
↓
INVALIDATION
```

এই behaviour backtest-এ test হবে।

---

## 28. RULE GROUP — REGIME

### REG-01 — Session

তোমার current chart framework:

```
UTC-4

Asia          19:00-22:00
London        02:00-05:00
New York      07:00-10:00
London Close  10:00-12:00
```

Architecture:

Session = Execution Priority

not:

Session = HTF Setup Validity

---

## 29. REG-02 — Volatility

Three states:

```
NORMAL
ELEVATED
EXTREME
```

Initial purpose:

```
NORMAL
→ normal execution

ELEVATED
→ caution / downgrade

EXTREME
→ potential block
```

Exact volatility metric:

ATR / percentile-based approach-এর মধ্যে পরে নির্বাচন করব।

---

## 30. REG-03 — News

Conceptual states:

```
NORMAL
CAUTION
BLOCK
```

কিছু Pine Script-এর বাস্তব data-access limitation আগে verify করতে হবে।

আমরা এমন economic-calendar detector বানাব না যেটা শুধু দেখতে impressive কিন্তু reliable নয়।

---

## 31. RULE GROUP — EXECUTION

### EXEC-01

30M execution শুরু হবে কেবল যখন:

```
HTF Context
+
Liquidity Event
+
Reclaim
+
Structural Confirmation
+
Valid POI
```

complete হয়েছে।

---

## 32. EXEC-02 — 30M-এর role

30M:

> Execution refinement

30M:

❌ Primary directional engine নয়।

---

## 33. EXEC-03 — Entry Candidate

Long:

```
1D bullish context
        +
4H sell-side sweep
        +
reclaim
        +
1H bullish structural confirmation
        +
valid bullish POI
        +
SMT not contradictory
        +
30M execution condition
```

→

```
LONG CANDIDATE
```

Short = mirror logic।

---

## 34. EXEC-04 — Final Entry Gate

```
                 ENTRY GATE
                     │
      ┌──────────────┼──────────────┐
      ↓              ↓              ↓
   Context        Structure        POI
      │              │              │
      └──────────────┼──────────────┘
                      ↓
                     SMT
                      ↓
                    Regime
                      ↓
                     30M
                      ↓
                    ENTRY
```

---

## 35. RULE GROUP — INVALIDATION

প্রতিটি setup-এর lifecycle:

```
ACTIVE
TRIGGERED
INVALIDATED
EXPIRED
```

Invalidated examples:

- Sweep thesis fails
- Reclaim fails
- Structural condition invalidates
- POI invalidates
- Opposing HTF condition becomes dominant
- Double Purge invalidation condition
- Extreme-risk regime

---

## 36. RULE GROUP — EXPIRY

Setup indefinite থাকবে না।

```
SETUP CREATED
        ↓
WAIT
        ↓
No confirmation within allowed window
        ↓
EXPIRED
```

Exact expiry:

Parameter — not yet locked.

---

## 37. MASTER SIGNAL LOGIC

এখন আমাদের সবচেয়ে গুরুত্বপূর্ণ pseudocode:

```
IF
    HTF_CONTEXT_VALID
AND
    LIQUIDITY_EVENT_VALID
AND
    RECLAIM_CONFIRMED
AND
    STRUCTURAL_CONFIRMATION_VALID
AND
    VALID_POI_EXISTS
AND
    REGIME_NOT_BLOCKED
AND
    EXECUTION_CONDITION_VALID

THEN

    EXECUTION_CANDIDATE = TRUE
```

তারপর:

```
SMT
SESSION
VOLATILITY
POI QUALITY
```

candidate quality modify করবে।

---

## 38. Master Engine কখন BUY বলবে?

LONG:

```
1D Context
        ↓
Bullish
        ↓
4H Sell-side liquidity event
        ↓
Reclaim
        ↓
1H Bullish CISD OR MSS
        ↓
Displacement qualification
        ↓
Bullish POI
        ↓
SMT ≠ contradictory
        ↓
Regime ≠ blocked
        ↓
30M execution
        ↓
LONG
```

---

## 39. Master Engine কখন SELL বলবে?

```
1D Context
        ↓
Bearish
        ↓
4H Buy-side liquidity event
        ↓
Reclaim
        ↓
1H Bearish CISD OR MSS
        ↓
Displacement qualification
        ↓
Bearish POI
        ↓
SMT ≠ contradictory
        ↓
Regime ≠ blocked
        ↓
30M execution
        ↓
SHORT
```

---

## 40. সবচেয়ে গুরুত্বপূর্ণ — NO TRADE ENGINE

আমাদের indicator-এর সবচেয়ে valuable output শুধু:

```
BUY
SELL
```

হবে না।

বরং:

```
LONG
SHORT
WAIT
NO TRADE
INVALID
EXPIRED
```

থাকবে।

কারণ market-এর বড় অংশে কোনো trade নেওয়া উচিত নয়।

---

## 41. Signal Quality Model

এখন আমি traditional "8/10 confluence" scoring ব্যবহার করছি না।

বরং:

**Tier A — Structural Validity**

```
Context
Liquidity
Reclaim
Structure
POI
```

**Tier B — Quality**

```
SMT
Displacement quality
POI quality
```

**Tier C — Execution**

```
Session
30M confirmation
Volatility
News regime
```

এতে একই concept multiple times count হওয়ার risk কমে।

---

## 42. Current Signal Classes

আমি provisionally:

```
A+
A
B
C
INVALID
```

রাখছি।

কিন্তু A+/A/B/C-এর exact numerical definition এখনো lock করছি না।

এটা গুরুত্বপূর্ণ—কারণ আমরা এখন যদি arbitrary 80%, 70%, 60% score বানাই, সেটা pseudo-precision হবে।


## 43. Final Architecture v1.0

<pre><code>┌───────────────────────────────────────┐
│             MACRO LAYER               │
│               1W / 1D                 │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│          LIQUIDITY EVENT LAYER        │
│                4H                     │
│      Range / Liquidity / Sweep        │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│           RECLAIM LAYER               │
│          CRT / C2 / Reclaim            │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│         STRUCTURE LAYER               │
│                1H                     │
│       CISD / MSS / Displacement       │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│       CROSS-MARKET VALIDATION         │
│            XAU ↔ XAG                  │
│                SMT                    │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│             POI LAYER                 │
│ FVG / IFVG / Breaker / Unicorn        │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│             REGIME LAYER              │
│ Session / Volatility / News           │
└───────────────────┬───────────────────┘
                    ↓
┌───────────────────────────────────────┐
│          EXECUTION LAYER              │
│                30M                    │
└───────────────────┬───────────────────┘
                    ↓
              ENTRY CANDIDATE</code></pre>
