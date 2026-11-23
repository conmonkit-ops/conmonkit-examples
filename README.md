# ConMon Kit example files

Example CSV files for the free checker at [conmonkit.com](https://conmonkit.com), which checks the monthly vulnerability report of a cloud provider in the FedRAMP programme.

- `template/` holds the empty template (header row only).
- `examples/01-clean.csv` has 8 records the checker accepts with no finding.
- `examples/02-common-mistakes.csv` has 10 records with typical mistakes; `02-common-mistakes.md` explains each one.
- `examples/03-larger.csv` has 40 valid records with mixed ratings and states.
- `COLUMNS.md` describes every column.

## Try them

1. Open [conmonkit.com](https://conmonkit.com) and go to the [checker](https://conmonkit.com/check/).
2. Choose "Build from a CSV", then choose one of the files.
3. Read the result.

The checker's page says: "Everything runs in your browser. Your files are never uploaded."

The dates in the files are fixed. Reminders about time limits can appear when you check them on a later date.

All data in these files is invented.

The checker reads the files against the schemas published at https://github.com/FedRAMP/schemas (versions 0.1.1, dated 2026-06-24, when these examples were made).

## Guides

- [From a spreadsheet to the three report files](https://conmonkit.com/guides/from-a-spreadsheet-to-the-three-report-files/)
- [The three evaluation decisions](https://conmonkit.com/guides/ratings-explained/)
- [Time limits by class](https://conmonkit.com/guides/deadlines-by-class/)
- [What the reports must contain](https://conmonkit.com/guides/what-the-reports-must-contain/)

Contact: support@conmonkit.com

ConMon Kit is an independent tool. It is not affiliated with or endorsed by FedRAMP or the U.S. General Services Administration (GSA).
