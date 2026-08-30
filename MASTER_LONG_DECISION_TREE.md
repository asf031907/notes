### MODULE I — 30M REFINEMENT

এখন 30M-এর কাজ:

**Better entry**

না:

**Different direction.**

অর্থাৎ:

<pre><code>1H = "I want to buy."
30M = "Where exactly?"</code></pre>
এটা architecture-এর সবচেয়ে clean formulation।

### ENTRY LOGIC

**LONG**

<pre><code>1W/1D context acceptable
        +
4H sell-side liquidity event
        +
bullish displacement
        +
1H CISD
        +
valid POI
        +
SMT not contradictory
        +
30M confirmation/refinement
        ↓
       LONG</code></pre>

**SHORT:**
exact inverse

### SMT-কে এখানে কীভাবে ব্যবহার করব?
আমি তিনটা research variant রাখছি:

**Variant A — Neutral**

SMT absent → trade allowed.

**Variant B — Weighted**

SMT present → score increases.

**Variant C — Strict**

SMT contradiction → reject.

এগুলো **backtest variants**

এতে আমরা empirically জানতে পারব SMT সত্যিই value যোগ করছে কিনা।

### STOP LOSS

SL হবে:

**Structural Invalidation**

Long:
<pre><code>Entry
 ↓
POI
 ↓
Sweep low / invalidation structure</code></pre>
Short:
<pre><code>Entry
 ↓
POI
 ↓
Sweep high / invalidation structure</code></pre>
Fixed $ amount নয়।

Fixed 20-pip type rule-ও নয়।

### TAKE PROFIT

Primary target:

**Opposing Liquidity**

Long:
<pre><code>Entry
 ↓
Next meaningful buy-side liquidity</code></pre>
Short
<pre><code>Entry
 ↓
Next meaningful sell-side liquidity</code></pre>
তারপর RR constraint থাকবে

### MINIMUM RR

আমি এখন 1:2 lock **করছি না।**

কারণ সেটা arbitrary।

আমরা backtest করব:

<pre><code>1:1.5
1:2
1:2.5
1:3</code></pre>
তারপর দেখব:

expectancy কোথায় সবচেয়ে ভালো?

### NO-TRADE CONDITIONS

এটা আমাদের engine-এর সবচেয়ে গুরুত্বপূর্ণ অংশ।

**No trade যদি:**
<pre><code>HTF conflict
OR
No meaningful liquidity
OR
No sweep
OR
No displacement
OR
No CISD
OR
POI invalid
OR
SMT contradiction (strict variant)
OR
RR inadequate
OR
setup already extended
OR
invalidation already breached</code></pre>

### SIGNAL GENERATION

আমি চাই না chart-এ 20টা label দেখা যাক।

বরং:

**WATCH**

<pre><code>“Potential bullish setup — waiting for CISD.”</code></pre>

**CONFIRMED**

<pre><code>“Bullish setup confirmed — waiting for execution.”</code></pre>

**ENTRY ACTIVE**

<pre><code>“Long execution zone active.”</code></pre>

**NO TRADE**

<pre><code>“Conditions insufficient.”</code></pre>

এটা practical।

### MASTER LONG DECISION TREE

<pre><code>
START
  │
  ▼
1W/1D context?
  │
  ├── No → NO TRADE
  │
  ▼
4H meaningful location?
  │
  ├── No → NO TRADE
  │
  ▼
Sell-side liquidity sweep?
  │
  ├── No → WATCH / NO TRADE
  │
  ▼
Bullish displacement?
  │
  ├── No → WATCH
  │
  ▼
1H CISD?
  │
  ├── No → WATCH
  │
  ▼
Bullish SMT?
  │
  ├── Contradiction → DOWNGRADE / REJECT
  │
  ▼
Valid POI?
  │
  ├── No → CONFIRMED → WAIT
  │
  ▼
30M refinement?
  │
  ├── No → 1H execution candidate
  │
  ▼
ENTRY ACTIVE
</code></pre>

### SHORT DECISION TREE

<pre><code>START
  │
  ▼
1W/1D context?
  │
  ▼
4H meaningful location?
  │
  ▼
Buy-side liquidity sweep?
  │
  ▼
Bearish displacement?
  │
  ▼
1H bearish CISD?
  │
  ▼
SMT validation
  │
  ▼
Valid POI?
  │
  ▼
30M refinement
  │
  ▼
SHORT</code></pre>

### সবচেয়ে গুরুত্বপূর্ণ Design Decision

আমাদের **final engine signal engine + explanation engine** দুটোই হবে।

উদাহরণ:
**BUY**
<pre><code>LONG
Score: 14/17

Why?

✓ 1D bullish context
✓ 4H sell-side liquidity swept
✓ 1H bullish displacement
✓ CISD confirmed
✓ Bullish XAG divergence
✓ IFVG POI
✓ 30M confirmation</code></pre>

এতে তুমি বুঝতে পারবে কেন **engine signal দিল।**

এটা তোমার “blindly follow করতে চাই না” requirement-এর জন্য অত্যন্ত গুরুত্বপূর্ণ।
