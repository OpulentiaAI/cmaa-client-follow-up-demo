---
name: cmaa-client-follow-up-demo
description: Build a CMAA/APEX client follow-up demo. Use for simulated Neoserra records, attention ranking, Context.dev research, success-story matching, advisor outreach, or scheduling.
---

# CMAA Client Follow-Up Demo

Build one convincing advisor workflow: find the client CMAA is most likely to lose, explain why the client needs attention, research what changed in the business, ground the next move in CMAA proof, and schedule an approved follow-up.

## Inputs

Ask only for inputs that materially change the result:

- the target application or demo surface;
- whether a Context.dev key is available;
- whether the user supplied approved client fixtures or wants synthetic records.

Use synthetic records when client-data authority is unclear. Treat every Neoserra-shaped identifier as simulated unless the user explicitly authorizes real data.

## Procedure

1. **Inspect the host.** Read the target repository's agent guidance, UI conventions, existing demo routes, and verification commands. Finish when the implementation boundary and runnable demo URL are known.

2. **Pin the scenario.** Use the RAMP Manufacturing/APEX scenario from [references/scenario.md](references/scenario.md) unless the user supplies a better fixture. Keep the story focused on poor post-intake follow-up rather than broad CRM replacement. Finish when one primary advisor journey and three supporting queue records are defined.

3. **Model the post-intake record.** Represent intake status, program, assigned advisor, requested support, last touch, outstanding commitments, first-meeting status, deadline, preferred language, and next milestone. Label synthetic values in the UI. Finish when every ranking input is visible or traceable to the record.

4. **Build the attention queue.** Apply the scoring contract in [references/ranking.md](references/ranking.md), sort highest need first, and show the contributing points beside each client. Finish when an advisor can explain the top ranking without reading code.

5. **Research current activity.** Keep `CONTEXT_DEV_API_KEY` server-side. Allowlist demo clients before sending requests. Retrieve public company identity, likely NAICS categories, and source-backed current activity; request fact checking when the API supports it. Finish when every displayed signal links to a public source.

6. **Degrade honestly.** When Context.dev is unavailable, return the last sourced snapshot and label it `Sourced demo snapshot`. Reserve `Context.dev live` for a successful live response. Finish when no fallback state can be mistaken for live detection.

7. **Match CMAA proof.** Rank approved public outcomes by overlap with the client's program, industry, and next milestone. Use the source pack in [references/sources.md](references/sources.md). Finish when each matched story links to its original source and states the relevant outcome without embellishment.

8. **Draft the next action.** Generate a concise message in the client's preferred language that names the open commitment, uses current public activity only when relevant, and offers concrete appointment times. Keep sending behind an advisor approval control. Finish when the message can be edited before any state changes.

9. **Close the loop.** On approval, mark the follow-up scheduled, store the selected time and next milestone, recalculate the score, and re-rank the queue. Finish when unresolved clients rise above scheduled work and a confirmation is visible.

10. **Prove the workflow.** Verify desktop and narrow layouts, client switching, score explanations, research labels, source links, message editing, time selection, approval, score reduction, and queue movement. Finish only when the exact end-to-end journey passes in a running browser.

## Output Contract

The demonstration is complete when it provides:

- a clearly simulated post-intake Neoserra view;
- a deterministic, explainable attention queue;
- live Context.dev enrichment or an explicitly labeled sourced fallback;
- source-linked CMAA success stories matched to client context;
- an editable follow-up draft and selectable appointment time;
- an approval action that changes status, score, milestone, and queue order;
- responsive browser evidence for the complete journey.

## Guardrails

- Use no real client PII without explicit authority.
- Keep API credentials and research requests server-side.
- State `Unknown` when evidence is absent; do not infer eligibility, certifications, awards, revenue, or private business conditions.
- Separate public evidence from simulated CRM fields.
- Keep production write-back hypothetical unless a real Neoserra or Salesforce connector is configured and authorized.
- Solve client follow-up first. Treat funnel analytics, CRA reporting, bank sponsorship, and CRM replacement as separate workstreams.

## Reference Pointers

- Load [references/scenario.md](references/scenario.md) when creating fixtures or demo copy.
- Load [references/ranking.md](references/ranking.md) when implementing or testing prioritization.
- Load [references/sources.md](references/sources.md) before adding CMAA claims or success stories.
