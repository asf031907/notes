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
