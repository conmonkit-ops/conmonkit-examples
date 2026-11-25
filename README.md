# ConMon Kit example files

Example CSV files for the free checker at [conmonkit.com](https://conmonkit.com), which checks the monthly vulnerability report of a cloud provider in the FedRAMP programme.

- `template/` holds the empty template (header row only).
- `examples/01-clean.csv` has 8 records with no error and no warning. If you leave the overview text empty, the checker adds one line for information that asks you to write one.
- `examples/02-common-mistakes.csv` has 10 records with typical mistakes; `02-common-mistakes.md` explains each one.
- `examples/03-larger.csv` has 40 records with mixed ratings and states.
- `COLUMNS.md` describes every column.

## Try them

1. Open [conmonkit.com](https://conmonkit.com) and go to the [checker](https://conmonkit.com/check/).
2. Choose "Build from a CSV".
3. Fill in the settings the checker needs: the certification class (A to D), the first day and the last day of the reporting period (one month, for example `2026-11-01` to `2026-11-30`) and the address of your Certification Package Overview. For a trial any full web address works, for example `https://example.test/package`.
4. Choose one of the files.
5. Read the result. If it says "The reports were not built.", the page lists what is missing in the settings or what stops the file from being read.

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
