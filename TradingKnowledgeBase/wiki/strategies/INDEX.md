# Trading Strategies — INDEX

> **Last Updated:** <!-- AI updates this date on every wiki refresh -->
> **Total Strategies:** 1
> **Active:** 0 | **Testing:** 1 | **Retired:** 0

---

## Strategy Registry

| Strategy | File | Status | Win Rate | Avg R | Sample | Validated |
|---|---|---|---|---|---|---|
| Strategy 1 | [[strategy1]] | 🟡 TESTING | — | — | 0 trades | ⚠️ No |

> ⚠️ A strategy is **VALIDATED** only after 20+ trades. Stats before that are directional only.

---

## Status Lifecycle

Every strategy moves through a defined lifecycle. Status changes must be logged in the strategy's Rule Change Log with the date and reason.

### 🟡 TESTING
A new or unproven setup being traded at **reduced size (25–50% of normal risk)** to gather data without significant capital exposure. The rules may still be evolving. No conclusions should be drawn until 20+ trades are logged.

- **Entry criteria:** You have a hypothesis and basic rules defined
- **Position size:** 25–50% of your normal risk per trade
- **Exit criteria:** Promote to ACTIVE after 20+ trades with positive expectancy, or RETIRE if edge is not confirmed after 30–40 trades
- **Mindset:** You are paying small tuition to learn whether this setup works for you

### 🟢 ACTIVE
A validated setup with 20+ trades, defined rules, and confirmed positive expectancy. Trade at **full normal size**. Rules are still allowed to evolve based on data, but the core edge is established.

- **Entry criteria:** 20+ trades logged, positive expectancy, rules are written and trusted
- **Position size:** Full normal risk per trade 
- **Exit criteria:** Move to PAUSED if market conditions shift against it, or RETIRE if a large new sample shows the edge has degraded

### 🔴 PAUSED
A previously ACTIVE strategy temporarily taken off the table. The edge may still exist but current conditions don't support it — or you are on a drawdown and need to step back without permanently retiring it.

- **Entry criteria:** Market conditions no longer suit the setup, or 3+ consecutive losing weeks
- **Position size:** Zero — not trading
- **Exit criteria:** Return to ACTIVE when conditions realign, or RETIRE if the pause reveals the edge was never real

### ⚫ RETIRED
Permanently removed from the playbook. The file stays in wiki/strategies/ as a record so you don't revisit the same idea and make the same mistake twice.

- **Entry criteria:** 30–40 trades with no positive expectancy, or consistent inability to execute correctly regardless of conditions
- **Position size:** Zero — never trading again
- **Note:** Document the reason clearly in the strategy file before retiring it

---

## Status Flow

```
New idea
   ↓
🟡 TESTING — 25-50% size, building sample (20+ trades)
   ↓ positive expectancy confirmed        ↓ no edge after 30–40 trades
🟢 ACTIVE — full size ($200 risk)        ⚫ RETIRED — documented, never traded again
   ↓ conditions shift or drawdown
🔴 PAUSED — temporarily off the table
   ↓ conditions return
🟢 ACTIVE again
```

> To promote or retire a strategy, run the relevant prompt from wiki/PROMPTS.md

---

## Performance Summary
> *AI updates this section during weekly wiki refresh*

**Best Expectancy:** —
**Worst Expectancy:** —
**Most Traded Setup:** —
**Highest Win Rate:** —
**Best Avg R:** —

---

## Market Condition Matrix
> *AI populates this as trade data accumulates*

| Setup | Trending | Choppy | Volatile | Slow Grind |
|---|---|---|---|---|
| Strategy 1 | — | — | — | — |

> ✅ = Works well | ⚠️ = Use caution | ❌ = Avoid | — = No data yet

---

## Time of Day Matrix
> *AI populates this as trade data accumulates*

| Setup | 8:00–10:00 | 10:00–12:00 | 12:00–2:00 | 2:00–4:00 |
|---|---|---|---|---|
| Strategy 1 | — | — | — | — |

---

## Wiki Files

### strategies/
- [[strategy1]] — Strategy 1 rules and stats

### setups/
> *AI creates files here as new entry patterns are identified from raw/charts/*

### lessons/
> *AI creates files here from EOD debriefs and weekly reviews*

### rules/
> *Run !rulebook once raw/ has sufficient material to generate this*
- Once created, [[master-rulebook]] — Universal rules that apply across all strategies

---

## Open Questions Across All Strategies
> *AI adds items here during health checks when data raises unresolved questions*

- [ ] What is the optimal time stop across all intraday setups?

---

*This file is maintained by AI. Do not edit manually. Run the weekly wiki refresh prompt to update all stats and dates.*
