---
name: cmaa-client-follow-up-demo
description: Run a CMAA/APEX follow-up demo from mock JSON. Use for Context.dev discovery, browser research, explainable rankings, success stories, and advisor reporting in Documents.
---

# CMAA Client Follow-Up Demo

Run one advisor-ready research workflow without building an application. The mock Neoserra-shaped records are already populated in [assets/cmaa-clients.json](assets/cmaa-clients.json); treat them as the fixed intake snapshot.

## Procedure

1. **Open the state.** Read the existing native Documents scratchpad at every start or resume. Create it once if absent, then append the run ID, input asset path, and current phase. Finish when later work can resume without relying on chat history.

2. **Load, do not invent.** Read `assets/cmaa-clients.json` and validate every required ranking input against [references/ranking.md](references/ranking.md). Preserve the records as supplied. Finish when all clients either pass validation or have an explicit data-quality warning.

3. **Discover with Context.dev.** Resolve each company from its domain or name and location, record the canonical domain, company description, likely NAICS codes, and discovery confidence, and preserve the raw Context.dev result as an artifact. Finish when every client is resolved or labeled `Unresolved`; never substitute browser guessing for discovery.

4. **Research in the browser.** Use browser automation to visit the discovered company site and relevant public pages. Capture only current, explicitly stated activity that creates a timely reason to reconnect: contracts, buyers, partners, certifications, products, hiring, expansion, or deadlines. Finish when every signal has a URL, observed date, and browser screenshot ready to embed in Documents.

5. **Rank transparently.** Apply [references/ranking.md](references/ranking.md) to the JSON fields, sort highest need first, and retain each point contribution. Finish when the total can be recalculated from the displayed factors.

6. **Build the ranking in Documents.** Create or update one native Document titled `CMAA Client Follow-Up Brief`. Add a scannable ranked table with score, status, top factors, current activity, and recommended next action, followed by the full point breakdown for each client. Finish when the table order matches the calculation and an advisor can understand the ranking without another artifact.

7. **Match success stories.** Browser-verify the CMAA sources in [references/sources.md](references/sources.md), then match stories by program, industry, and next milestone. Finish when each selected story has an original source, exact reported outcome, and a sentence explaining the match.

8. **Complete the Documents output.** In the same `CMAA Client Follow-Up Brief`, add the Context.dev discovery table, browser-researched activity with embedded screenshots, matched success stories, advisor-ready follow-up drafts, suggested appointment windows, and data-quality caveats. Attach or quote the raw discovery results in the Document rather than reporting them elsewhere. Append the Document ID to the scratchpad.

9. **Verify the deliverable.** Re-read the final Document, open every embedded screenshot and source link, and compare the ranking table against the JSON calculation. Finish only when the Document contains the complete demo and requires no external report, visual artifact, or unshipped code.

## Required Outputs

One `CMAA Client Follow-Up Brief` in the Documents pane containing:

- raw Context.dev discovery results and the normalized discovery table;
- browser-research notes, source URLs, observed dates, and embedded screenshots;
- the ranked client table and every score contribution;
- matched, source-backed success stories;
- advisor follow-up drafts and scheduling recommendations;
- data-quality caveats and unresolved items.

The native Documents scratchpad must close with the final brief's Document ID and completion state.

## Guardrails

- Use the bundled JSON as simulated intake data; use no private client data.
- Use Context.dev for discovery and the browser for research. Keep those evidence lanes distinct.
- Mark absent evidence `Unknown` and failed discovery `Unresolved`.
- Preserve raw results and screenshot evidence inside Documents rather than a code repository or separate report.
- Build no HTML artifact, Next.js route, dashboard, database, connector, or production write-back.
- Treat scheduling as an advisor recommendation unless an authorized calendar connector is present.

## Reference Pointers

- Load [references/scenario.md](references/scenario.md) for the demo narrative.
- Load [references/ranking.md](references/ranking.md) before calculating scores.
- Load [references/sources.md](references/sources.md) before matching success stories.
