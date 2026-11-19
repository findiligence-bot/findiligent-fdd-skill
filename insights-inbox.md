# Insights inbox

Holding area for lines and insights the author shares during the week. Nothing here is part of the skill yet.

**Chat convention:** a message the author wraps in inverted commas ("...") is an insight to log. Claude replies with one word ("Noted"), runs no commands and adds no analysis. A message without inverted commas is a normal request that Claude acts on.

**Daily save (about 9:43 pm IST):** every quoted insight shared since the last save is added to "Pending" below, then committed and pushed in one go.

Each weekly run (Saturday evening IST) does the following:

1. Paraphrases each insight. External wording is never copied (D29).
2. Routes it to the right file. A deterministic rule goes to a definition file and an interpretive pattern goes to a pattern file. A method choice goes to `design-decisions.md`. A general lesson on how to think or interpret goes to `references/analyst-lenses.md` (IDs AL01 onward). That file is created on the first such insight and indexed in SKILL.md, so it applies to every analysis.
3. Labels it by origin: [Author], [Book], [GAAP] or [Claude]. Claude-proposed patterns stay in draft until the author approves them (D32).
4. Bumps the version in README and opens a pull request.
5. Moves the processed entries to the log below.

## Pending

<!-- Format: - YYYY-MM-DD — insight (source, if any) -->

- 2026-11-18 — "Money that arrives only because something else is falling can leave just as quickly" (source: author, to confirm). Proposed route: Analyst Lens AL01, with a link to the cash conversion patterns. Proposed reading: cash released by shrinkage (receivables or inventory falling with sales, lower capex, asset sales, cuts in spend) is not cash earned. It reverses when the business grows again, so test whether an operating cash inflow comes from earnings or from contraction.
- 2026-11-19 — "Job as investors is to ask whether the cash flows and balance sheet of the business have changed. If they have not, the volatility tends to pass. if they have, one must act, whatever the size of the company" (source: author, to confirm). Proposed route: Analyst Lens AL02. Proposed reading: separate price or news noise from a change in fundamentals. When a stock or result moves, test whether cash generation or the balance sheet (leverage, liquidity, obligations) has actually shifted. If not, treat it as noise. If so, act, and do not excuse it because the company is large.
- 2026-11-19 — "Hotel Industries - Q2FY27 was the industry best quarter in last 10 quarters in terms of revenue earned per available room (RevPAR), a key measure of hotel performance. growth came equally from more rooms being occupied and higher room rates. Key drivers includes, domestic travel, helped offset some weakness from International travellers not coming in. HIgher airfares, geoplitical tension has affected airline capacity and travel plans on certain international routes. But domestic travllers have continued to take holidays, while companies and event organizer have kept demand for hotel rooms and banquet facilities going. " (source: to confirm). Proposed route: new sector KPI guide for hotels (README lists sector KPI guides as planned), stored as dated sector context rather than a rule. Proposed reading: break RevPAR into occupancy and ARR (average room rate); growth from both is higher quality than growth from rate alone. Split the demand mix (domestic leisure, corporate, MICE and banquets, foreign tourists), since airline capacity and geopolitics hit foreign arrivals. Also check revenue outside rooms (F&B, banquets).

## Processed

| Week | Insight (short) | Went to | PR |
| --- | --- | --- | --- |
