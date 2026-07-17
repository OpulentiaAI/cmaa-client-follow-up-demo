# Attention Ranking Contract

Calculate the score from visible record fields. Cap the total at 100 and sort descending.

| Factor | Points |
| --- | --- |
| Days since last touch | `min(days × 2, 20)` |
| Overdue commitments | `min(count × 12, 24)` |
| No scheduled follow-up | 18 |
| First meeting not booked | 15 |
| Opportunity due within 14 days | 15 |
| Opportunity due within 15–30 days | 8 |
| Incomplete required intake fields | `min(count × 3, 12)` |
| Current public business signal | 8 |

Tie-break equal scores by putting clients without a scheduled follow-up first. Preserve stable source order after that.

## Required calculation checks

- RAMP Manufacturing scores 92 and ranks first.
- Casa Verde Facilities scores 62 and ranks second.
- Mekong Kitchen Collective scores 55 and ranks third.
- Hanul Commerce Studio scores 18 and ranks fourth.
- Every nonzero factor appears in the Documents ranking and explanation.
- Story matching returns Chicago Flavas for the primary APEX scenario.

If a calculated total differs, stop and reconcile the JSON fields against this table before finalizing the Document.
