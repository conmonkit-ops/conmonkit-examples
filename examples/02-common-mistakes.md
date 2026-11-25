# Common mistakes in 02-common-mistakes.csv

The file has 10 records, all invented. Row numbers count the header as row 1, so the first record is row 2. Open the file in ConMon Kit to see the checker report each one.

| Row | Tracking ID | What is wrong | How to correct it |
|---|---|---|---|
| 2 | EX-101 | `detected_at` is a plain date, `2026-11-03`. | Write a date and a time with seconds and an offset, for example `2026-11-03T09:00:00Z`. |
| 3 | EX-102 | `detection_source` is empty, and it is required. | Say which tool or activity found the vulnerability, for example `Weekly container scan`. |
| 4 | EX-103 | The rating `N7` is outside the allowed range. | Use a rating from `N0` to `N5`, for example `2026-11-06T09:00:00Z=N3`. |
| 5 | EX-104 | `likely_exploitable` says `maybe`. | Use `yes`, `no`, `true` or `false`. The answer is a decision for a person to make. |
| 6 | EX-105 | `disposition` says `Done`, which is not on the list. | Use `Fully Mitigated`, `Partially Mitigated`, `Remediated` or `False Positive`. |
| 7 | EX-106 | `accepted_at` is filled in but `acceptance_rationale` is empty. | Fill in both columns, or empty both. Write why the vulnerability is accepted. |
| 8 | EX-107 | The evaluation is recorded but the likely-exploitable answer is missing. | Record the `likely_exploitable` answer (`yes` or `no`). |
| 9 | EX-108 | The reduction date for its rating has passed and there is no overdue explanation (the checker also shows a reminder that the reduction is late). | Reduce the rating if the work is done, or write the reason in `overdue_explanation`. |
| 10, 11 | EX-109 | Two rows use the same tracking ID. Both rows are left out until this is fixed. | Give each row its own `tracking_id`, for example `EX-109` and `EX-110`. |

Rows 2 to 7 are caught when the file is read. They are listed under "Problems in the CSV" and left out of the files. Rows 8 to 11 are caught when the records are checked, so they appear as findings.

Use a reporting period of one month, for example first day `2026-11-01` and last day `2026-11-30`. A longer period adds a warning of its own.

The checker has no setting for the date of the check: it uses the moment the reports are built, which is as soon as you choose the file. Only row 9 (EX-108) depends on it. Its reduction date depends on the certification class: 2026-11-22, 09:00 UTC for classes A and B, 2026-11-06, 09:00 UTC for class C and 2026-10-29, 09:00 UTC for class D. On any later day the checker shows one error (no overdue explanation) and one warning (the reduction is late). The other rows give the same result on any day.

If you leave the overview text empty, the checker adds one line for information that asks you to write one.
