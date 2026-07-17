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

## Scheduling transition

Approval must:

1. set `hasScheduledFollowUp` to `true`;
2. set the follow-up state and selected time;
3. clear overdue commitments represented by the approved follow-up;
4. change the next milestone to the scheduled session;
5. recalculate the score and queue order.

Scheduling does not erase inactivity, an uncompleted first meeting, intake gaps, or a real deadline. The remaining score should continue to explain those unresolved conditions.

## Minimum tests

- the primary RAMP fixture ranks first before scheduling;
- every nonzero factor appears in the explanation;
- scheduling lowers RAMP's score;
- an unresolved client outranks RAMP when the resulting scores tie;
- story matching returns Chicago Flavas for the primary APEX scenario.
