# Knowledge Base — Master Prompt Library

> All prompts are run in **Claude Code** or **Cursor** with your `TradingKnowledgeBase/` folder open.
> Replace anything in `[SQUARE BRACKETS]` with your own values before running.
> This file is for your reference only — the AI does not update it.

---

## One-Time Setup

### 1 — Build Initial Wiki
> Run first, on day one after `raw/` has content. Let it finish completely before running anything else.

```
Read everything in raw/. Compile a wiki in wiki/ following the rules in AGENTS.md.
Then do the following in order:

1. Create wiki/strategies/INDEX.md listing every strategy with its status,
   win rate, avg R, sample size, and validated flag. Use the existing
   wiki/strategies/INDEX.md as the starting structure if it exists.

2. Create wiki/setups/INDEX.md listing every entry pattern identified from
   raw/charts/. If no patterns are identifiable yet, create the file with
   empty registry tables ready to be populated.

3. Create wiki/lessons/INDEX.md listing every lesson extracted from
   raw/market-notes/. If no lessons are identifiable yet, create the file
   with empty registry tables ready to be populated.

4. Create one .md file per strategy in wiki/strategies/, one .md file per
   setup pattern in wiki/setups/, and one .md file per lesson in
   wiki/lessons/. Follow the template structure in any existing .md files.

Link related files using [[filename]] format. When done, list every file
created and flag anything that needs my attention.
```

### 2 — Build Master Rulebook
> Run after: AGENTS.md risk parameters are filled in, at least one strategy file has rules written out, and you have a week or two of EOD debriefs in raw/market-notes/. Do not run this on day one — the AI needs real material to synthesize from.

```
Read everything in raw/ and wiki/strategies/. Based on my trading rules, risk
parameters in AGENTS.md, and any rules mentioned across my strategy files, create
wiki/rules/master-rulebook.md. It should contain universal rules that apply across
all strategies — things like daily loss limits, position sizing, when not to trade,
and any behavioral rules that appear repeatedly in my notes.
```

---

## Daily Prompts

### End of Day Update
> Run once every evening after logging trades, adding screenshots, and filling in the EOD Debrief.

```
Read all new content added today across raw/trades/TradeLog_KnowledgeBase.xlsx,
raw/charts/ChartScreenshotNotes.xlsx, and raw/market-notes/. Then do all of
the following:

1. TRADES — For each strategy with new trades, recalculate win rate, avg
   R-multiple, expectancy, and sample size. Update the corresponding strategy
   file in wiki/strategies/ and the Strategy Registry and Performance Summary
   in wiki/strategies/INDEX.md. Flag any strategy under 20 trades as
   ⚠️ UNVALIDATED.

2. SCREENSHOTS — Group new chart screenshots by setup type. Note any patterns
   in wins vs losses. Update wiki/setups/ with new observations. Create a new
   setup file if a pattern appears that doesn't have one yet.

3. MARKET NOTES — Extract any meaningful lesson from today's pre-market prep
   and EOD debrief. Add it to wiki/lessons/ if worth keeping. Update any
   strategy file in wiki/strategies/ if today's data confirms or contradicts
   an existing rule.

Tell me which files were updated and flag anything that needs my attention.
```

---

## Weekly Prompts
> Run every Friday. Run in order.

### 1 — Weekly Performance Summary

```
Read raw/trades/ for this week's trades and raw/market-notes/ for this week's
daily notes. Summarize: (1) which setups performed best and worst, (2) what
market conditions dominated this week, (3) whether my setups are being used in
the right conditions, (4) any rule I appeared to break based on the trade notes.
Save the summary to outputs/reports/[YYYY-MM-DD]-weekly-summary.md
```

### 2 — Setup Deep Dive
> Replace [SETUP NAME] with whichever setup had the most trades this week.

```
For the setup "[SETUP NAME]" analyze all trades this week in raw/trades/: win
rate, average R, market conditions on wins vs losses, time of day on wins vs
losses, and any common factors in losing trades. Does the data suggest any rule
should change? Show me the specific trades you are basing this on. Save to
outputs/refinements/[YYYY-MM-DD]-[setup-name]-analysis.md
```

### 3 — Weekly Wiki Refresh

```
Update wiki/strategies/ with this week's cumulative stats from raw/trades/. For
each strategy with 5+ trades, recalculate: win rate, avg R-multiple, expectancy,
sample size, and best/worst market conditions. Update the Market Condition Matrix
and Time of Day Matrix in wiki/strategies/INDEX.md. Update the Performance
Summary block. Note any strategies that just crossed the 20-trade validation
threshold and update their Validated status accordingly.
```

### 4 — Save Lessons Back to Knowledge Base

```
Based on this week's trades, debriefs, and the weekly review in outputs/reports/,
identify the top 3 lessons learned this week. Save them to
wiki/lessons/[YYYY-MM-DD]-weekly-lessons.md with the trade data that supports
each lesson. Then check if any existing lesson in wiki/lessons/ is now confirmed
by additional data and update it.
```

---

## Monthly Prompts
> Run on the last trading day of each month. Run in order.

### 1 — Monthly Health Check

```
Review the entire wiki/ directory. Do the following: (1) flag any strategy with
fewer than 20 trades as ⚠️ UNVALIDATED, (2) find any contradictions between
strategy files, (3) identify topics mentioned but never explained with a full
article, (4) list any claims in wiki/ that are not backed by data in raw/trades/,
(5) suggest 3 specific things to track or research next month. Save the full
report to outputs/reports/[YYYY-MM]-health-check.md
```

### 2 — Monthly Strategy Ranking

```
Using all trade data in raw/trades/, rank every strategy by expectancy
(win% × avg win$ minus loss% × avg loss$). For each strategy show: trades taken,
win rate, avg R, expectancy, and market condition it performs best in. Flag any
strategy with negative expectancy that I should consider stopping or moving to
PAUSED. Save to outputs/reports/[YYYY-MM]-strategy-ranking.md
```

### 3 — Monthly Rule Audit

```
Read wiki/strategies/ and wiki/rules/. For each rule currently in my strategy
files, find trades in raw/trades/ where I broke that rule. What was the outcome
of those trades? Which rules am I breaking most often, and what is the P&L impact
of breaking them vs following them? Save to outputs/reports/[YYYY-MM]-rule-audit.md
```

### 4 — Market Condition Analysis

```
Cross-reference raw/trades/TradeLog_KnowledgeBase.xlsx with the Market Condition
field in each YYYY-MM-DD-notes.md file in raw/market-notes/. For each market type
(Trending, Choppy, Volatile, Slow Grind), what is my win rate and avg R per
setup? Which setups should I avoid in choppy markets? Which setups are strongest
in trending markets? Update the Market Condition Matrix in
wiki/strategies/INDEX.md with these findings. Save full analysis to
outputs/reports/[YYYY-MM]-market-conditions.md
```

---

## On-Demand Prompts
> Run any time you need a specific analysis.

### Single Setup Deep Dive

```
Analyze all trades tagged "[SETUP NAME]" in raw/trades/. Show me: win rate, avg R,
expectancy, time-of-day breakdown (8:00–9:30 open vs 9:30–11:00 mid-morning vs 11:00–12:00 late window), 
market condition breakdown, and the 3 most common characteristics of losing trades. 
Based on this, should any entry rules, exit rules, or filters change? Show the specific trade
data supporting each recommendation.
```

### Losing Streak Diagnosis

```
I have had [X] consecutive losing trades. Read raw/trades/ for those trades and
raw/market-notes/ for those days. Diagnose whether this is: (1) a strategy
problem — the setup stopped working, (2) an execution problem — I am not following
my rules, (3) a market conditions problem — conditions do not suit my setups, or
(4) a sample size issue — normal variance. Give me a specific recommendation for
what to do next.
```

### Knowledge Gap Analysis

```
Based on everything in wiki/, what are the three biggest gaps in my understanding
of day trading that could be limiting my performance? For each gap, suggest what
I should research, track, or practice to fill it. Also suggest 3 new articles
that would add value to the wiki based on what is missing.
```

### Rule Change — Update Wiki
> Run after you have decided to change a rule. Fill in all three brackets.

```
Update wiki/strategies/[STRATEGY-FILENAME].md — I have changed the [RULE NAME]
rule from "[OLD RULE]" to "[NEW RULE]" because [REASON / TRADE THAT CAUSED IT].
Log this change in the Rule Change Log section of that file with today's date.
If this rule change affects the Disqualifiers, Entry Rules, or Exit Rules sections,
update those too.
```

### Save Answer Back to Knowledge Base
> Run after any AI analysis you want to preserve and build on.

```
Save your previous answer as outputs/[topic]-[YYYY-MM-DD].md. Then update the
relevant articles in wiki/ to incorporate any new insights, confirmed patterns,
or rule changes identified in that answer. Update wiki/strategies/INDEX.md if
any new files were created.
```

### Generate a Trading Briefing

```
Write a 500-word briefing on [TOPIC] using only information from wiki/ and raw/.
Include: what I currently know, what the data says, what is still uncertain, and
what I should do next. Save to outputs/[topic]-briefing.md
```

### Compare Two Sources

```
Compare what raw/[SOURCE A] says about [CONCEPT] vs raw/[SOURCE B]. Where do they
agree? Where do they disagree? Which view does my actual trade data in raw/trades/
support? Save the comparison to outputs/[concept]-comparison.md
```

### Promote a Strategy from TESTING to ACTIVE

```
Read wiki/strategies/[STRATEGY-FILENAME].md and all trades tagged "[STRATEGY NAME]"
in raw/trades/. Confirm: (1) there are 20+ trades logged, (2) expectancy is
positive, (3) all rule sections in the strategy file are fully filled in. If all
three are true, update the strategy file status to 🟢 ACTIVE and update the
Strategy Registry table in wiki/strategies/INDEX.md accordingly. Log the
promotion in the strategy's Rule Change Log with today's date.
```

### Retire a Strategy

```
Update wiki/strategies/[STRATEGY-FILENAME].md status to ⚫ RETIRED. Add a
Retirement Summary section at the top of the file documenting: total trades taken,
final win rate, final expectancy, and the reason for retirement. Update the
Strategy Registry table in wiki/strategies/INDEX.md. Do not delete the file.
```

---
 
*This file lives at wiki/PROMPTS.md — do not move it.*
