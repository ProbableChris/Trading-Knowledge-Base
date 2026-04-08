# Day Trading — Personal Knowledge Base

## What This Is
A personal knowledge base for developing, testing, and refining intraday day trading strategies.
The goal is to identify what setups have a statistical edge, eliminate what doesn't work, and
build a consistent, rule-based approach. Every rule change is tracked with data.

## Folder Structure
- raw/ contains all unprocessed source material. Never modify these files.
 - raw/charts/        → Chart screenshots. Named: YYYY-MM-DD-TICKER-setup-name-OUTCOME.png
 - raw/data/          → Price data CSVs, scan exports, watchlists, broker exports
 - raw/trades/        → Trade journals and logs (TradeLog_KnowledgeBase.xlsx)
 - raw/market-notes/  → Daily pre-market prep and EOD debrief files
 - raw/research/      → Articles, strategy notes, book excerpts, course notes
- wiki/ contains the organized, AI-maintained knowledge base.
 - wiki/strategies/   → One .md file per strategy (rules, stats, change log)
 - wiki/setups/       → Specific entry pattern breakdowns
 - wiki/lessons/      → Mistakes, lessons learned, key insights
 - wiki/rules/        → Your master rulebook (evolves over time)
- outputs/ contains AI-generated reports, backtests, and refinements.
 - outputs/reports/   → Weekly reviews, monthly health checks
 - outputs/refinements/ → AI-generated strategy refinement reports
 - outputs/backtests/ → Backtest results and analysis

## Wiki Rules
- Every strategy gets its own .md file in wiki/strategies/
- Every wiki file starts with a one-paragraph summary
- Link related strategies using [[strategy-name]] format
- Link related setups using [[setup-name]] format
- Link related lessons using [[lesson-name]] format
- Maintain an INDEX.md in wiki/strategies/ listing every strategy
- When new trades or data are added, update the relevant strategy files
- Track win rate, avg R, and sample size on every strategy page
- Flag any strategy with fewer than 20 trades as ⚠️ UNVALIDATED

## My Trading Focus <!-- Modify the Trading Focus As Needed -->
- Active Hours For Entry: 8:00am-12:00pm EST
- Style: Day Trading (intraday — all positions closed by 1pm ET)
- Universe: Nasdaq-100 Micro (MNQ)
- Timeframes: 1-min
- Strategies: Strategy 1

## Strategy Evaluation Criteria
When analyzing any strategy or setup, always evaluate:
1. Win Rate 
2. Average R-Multiple on wins 
3. Expectancy = (Win% × Avg Win $) - (Loss% × Avg Loss $)
4. Max consecutive losses (for position sizing / drawdown planning)
5. Market conditions it works best in (trending vs choppy vs volatile)
6. Time of day it works best (open, mid-day, close)
7. Sample size — minimum 20 trades before drawing conclusions

## Chart Screenshot Convention
Filenames: YYYY-MM-DD-TICKER-setup-name-OUTCOME.png
Example: 2024-03-15-NVDA-bull-flag-breakout-WIN.png
Always include a matching row in raw/charts/ChartScreenshotNotes.xlsx

## Trade Log Format
All trades logged in raw/trades/TradeLog_KnowledgeBase.xlsx
Key fields: Date, Ticker, Direction, Setup Name, Entry, Stop, Target, Exit,
Shares, Risk $, P&L $, R-Multiple, Win/Loss, Market Condition, Timeframe, Notes

## Wiki Maintenance Rules
Every strategy page must contain:
- Summary paragraph
- Current Rules (entry, exit, filters)
- Performance Stats (win rate, avg R, sample size, expectancy)
- Works Best When (market conditions)
- Fails When (conditions to avoid)
- Open Questions (what still needs more data)
- Rule Change Log (date-stamped history of every rule change and why)

## Risk Parameters
- Risk per trade: <!-- add risk value -->
- Daily loss limit: <!-- add daily loss limit if desired, or delete this line -->
- Max position size: Never risk more than the 'Risk per trade', sizing reflects max size that can be obtained risking 'Risk per trade'

## Prompt Shortcuts

When I type any of the following commands, run the corresponding prompt exactly
as written in wiki/PROMPTS.md, and for any prompt with a [ ] such as "[YYYY-MM]", ask me to confirm the details that should be in [ ]:

- `!initial`  → Run the Build Initial Wiki prompt
- `!daily`    → Run the End of Day Update prompt
- `!weekly`   → Run all 4 Weekly prompts in order from wiki/PROMPTS.md.
- `!monthly`  → Run all 4 Monthly prompts in order from wiki/PROMPTS.md.
- `!health`   → Run the Monthly Health Check prompt only
- `!rank`     → Run the Monthly Strategy Ranking prompt only
- `!audit`    → Run the Monthly Rule Audit prompt only
- `!gaps`     → Run the Knowledge Gap Analysis prompt
- `!rulebook` → Run the Build Master Rulebook prompt
- `!deep [SETUP NAME]` → Run the Single Setup Deep Dive prompt for that setup
- `!diagnose` → Run the Losing Streak Diagnosis prompt
