# Federal U.S. Code — folder plan (decided 2026-10-31)

- Own top-level folder, separate from any state folder: `codes/FEDERAL/`
- One file per U.S. Code title (54 titles), e.g. `usc-title-18.json`
  (Crimes and Criminal Procedure), `usc-title-42.json` (Public Health
  and Welfare), `usc-title-05.json` (Government Organization).
- Split further by chapter if any single title approaches GitHub's
  100 MB per-file limit (none is expected to as plain text/JSON).
- Official source: uscode.house.gov / govinfo. Version/date the
  snapshot; the U.S. Code is updated, so record the edition date in
  each file.
- Bot routing: a federal question (e.g. "42 U.S.C. § 1983") loads
  only that title's file, never the whole federal set.
- Capacity: the full U.S. Code as plain text is estimated in the
  low hundreds of megabytes total, split across 54 title files —
  comfortably under the per-file limit, and under GitHub Pages' ~1 GB
  site recommendation on its own. It is the all-50-states full text
  combined that would push a single Pages site past that ceiling,
  not the federal set alone.
