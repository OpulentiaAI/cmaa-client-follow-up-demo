---
name: cmaa-client-follow-up-demo
description: Run a CMAA/APEX follow-up demo from mock JSON. Use for Context.dev discovery, browser research, ranking visuals, screenshots, success stories, or advisor outputs in Documents.
---

# CMAA Client Follow-Up Demo

Run one advisor-ready research workflow without building an application. The mock Neoserra-shaped records are already populated in [assets/cmaa-clients.json](assets/cmaa-clients.json); treat them as the fixed intake snapshot.

## Procedure

1. **Open the state.** Read the existing native Documents scratchpad at every start or resume. Create it once if absent, then append the run ID, input asset path, and current phase. Finish when later work can resume without relying on chat history.

2. **Load, do not invent.** Read `assets/cmaa-clients.json` and validate every required ranking input against [references/ranking.md](references/ranking.md). Preserve the records as supplied. Finish when all clients either pass validation or have an explicit data-quality warning.

3. **Discover with Context.dev.** Resolve each company from its domain or name and location, record the canonical domain, company description, likely NAICS codes, and discovery confidence, and preserve the raw Context.dev result as an artifact. Finish when every client is resolved or labeled `Unresolved`; never substitute browser guessing for discovery.

4. **Research in the browser.** Use browser automation to visit the discovered company site and relevant public pages. Capture only current, explicitly stated activity that creates a timely reason to reconnect: contracts, buyers, partners, certifications, products, hiring, expansion, or deadlines. Finish when every signal has a URL, observed date, and browser screenshot.

5. **Rank transparently.** Apply [references/ranking.md](references/ranking.md) to the JSON fields, sort highest need first, and retain each point contribution. Finish when the total can be recalculated from the displayed factors.

6. **Create the ranking visual.** Produce one lightweight HTML or native visual artifact—not an application—with the ranked queue, scores, factor breakdowns, current activity, and source links. Open it in the browser at desktop and narrow widths and capture both screenshots. Finish when the screenshots are readable and show the same ordering as the calculation.

7. **Match success stories.** Browser-verify the CMAA sources in [references/sources.md](references/sources.md), then match stories by program, industry, and next milestone. Finish when each selected story has an original source, exact reported outcome, and a sentence explaining the match.

8. **Write the Documents output.** Create or update one native Document titled `CMAA Client Follow-Up Brief`. Include the ranked queue, score explanations, Context.dev discovery table, browser-researched activity with screenshot links, matched success stories, advisor-ready follow-up drafts, suggested appointment windows, and data-quality caveats. Append the Document ID to the scratchpad.

9. **Verify the deliverables.** Re-read the final Document, open every screenshot and source link, and compare the ranking table against the JSON calculation. Finish only when the Document and screenshots form a complete demo without referring to unshipped code.

## Required Outputs

- raw Context.dev discovery results;
- browser-research notes with source URLs and observed dates;
- a desktop ranking screenshot;
- a narrow/mobile ranking screenshot;
- one `CMAA Client Follow-Up Brief` in the Documents pane;
- matched, source-backed success stories;
- advisor follow-up drafts and scheduling recommendations;
- a scratchpad closeout entry listing every artifact and unresolved item.

## Guardrails

- Use the bundled JSON as simulated intake data; use no private client data.
- Use Context.dev for discovery and the browser for research. Keep those evidence lanes distinct.
- Mark absent evidence `Unknown` and failed discovery `Unresolved`.
- Preserve raw results and screenshot evidence; summarize them in Documents rather than a code repository.
- Build no Next.js route, dashboard, database, connector, or production write-back.
- Treat scheduling as an advisor recommendation unless an authorized calendar connector is present.

## Reference Pointers

- Load [references/scenario.md](references/scenario.md) for the demo narrative.
- Load [references/ranking.md](references/ranking.md) before calculating scores.
- Load [references/sources.md](references/sources.md) before matching success stories.
