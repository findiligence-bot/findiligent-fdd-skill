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

## Processed

| Week | Insight (short) | Went to | PR |
| --- | --- | --- | --- |
