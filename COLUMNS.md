# Columns of the ConMon Kit CSV template

One row per vulnerability, one header row, UTF-8. Keep the header exactly as in `template/vulnerability-records-template.csv` (same names, same order). Column names are not case sensitive, but a name that is not in the list, or that appears twice, is reported. Row 1 is the header, so the first record is row 2.

Time values use the form `2026-11-01T09:30:00Z`: date, `T`, time with seconds, then an offset (`Z` means UTC). A plain date is not enough, except in `kev_due_date`.

| Column | Required or optional | Format / allowed values | Meaning | Example |
|---|---|---|---|---|
| `tracking_id` | Required | Text, unique in the file | Your own identifier for the vulnerability | `EX-001` |
| `description` | Required | Free text | Short description of the flaw | `Example finding: outdated library in the example billing-api.` |
| `detected_at` | Required | Time with seconds and an offset | When the vulnerability was detected | `2026-11-01T09:30:00Z` |
| `detection_source` | Required | Free text | The tool or activity that found it | `Weekly container scan` |
| `evaluation_completed_at` | Optional | Time with seconds and an offset, not earlier than `detected_at` | When your evaluation finished | `2026-11-02T09:30:00Z` |
| `internet_reachable` | Optional | `yes`, `no`, `true` or `false` | Your answer: can it be reached from the internet | `no` |
| `likely_exploitable` | Optional | `yes`, `no`, `true` or `false` | Your answer: is it likely to be exploited | `no` |
| `potential_agency_impact` | Optional | Free text | Short note on the impact for agencies | `Limited to a single example service.` |
| `rating_events` | Optional | `time=N#` pairs separated by `;`, oldest first, rating `N0` to `N5` | The rating over time; the last pair is the current rating | `2026-11-02T09:30:00Z=N3;2026-11-09T09:30:00Z=N2` |
| `next_reduction_at` | Optional, goes with `next_reduction_target` | Time with seconds and an offset | When the next rating reduction is expected | `2026-12-10T00:00:00Z` |
| `next_reduction_target` | Optional, goes with `next_reduction_at` | `N0` to `N5` | The rating expected after that reduction | `N1` |
| `accepted_at` | Optional, goes with `acceptance_rationale` | Time with seconds and an offset | When it became an accepted vulnerability | `2026-09-05T09:00:00Z` |
| `acceptance_rationale` | Optional, goes with `accepted_at` | Free text | Why it is accepted | `The endpoint is retired next year and extra monitoring is in place.` |
| `closed_at` | Optional, goes with `disposition` | Time with seconds and an offset | When it was closed | `2026-11-20T09:00:00Z` |
| `disposition` | Optional, goes with `closed_at` | `Fully Mitigated`, `Partially Mitigated`, `Remediated` or `False Positive` | How it was closed | `Remediated` |
| `overdue_explanation` | Optional | Free text | Why it is overdue, if it is | `Waiting for a vendor release.` |
| `supplementary_risk_information` | Optional | Free text | Anything that helps agencies judge the risk | `No agency data appears in the error page.` |
| `kev_due_date` | Optional | A date (`2026-11-25`) or a time with an offset | Due date from the CISA Known Exploited Vulnerabilities catalogue, if it is listed there | `2026-11-25` |

Notes

- "Goes with" means fill in both columns or neither.
- Leave an optional cell empty until you have the answer. Once `evaluation_completed_at` is filled, the checker reports an error for each of `likely_exploitable`, `internet_reachable` and a rating that is still missing.
- Ratings and the yes/no answers are decisions for people. ConMon Kit reads them as you write them.
- Do not put sensitive technical detail (addresses, host names, secrets) into the text columns; the checker warns about text that looks like that.
