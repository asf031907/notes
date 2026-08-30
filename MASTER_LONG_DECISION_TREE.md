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
