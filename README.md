# US school days by state (2026-27): minimum days and hours, CSV + JSON

The minimum number of instructional days and hours each US state and DC requires in a school year, with the law or rule behind every row. 51 rows.

The table was built by opening the current statute or state board rule for every state in October 2026 (state code on the legislature site, or the education department page that quotes it), starting from the Education Commission of the States list of January 2023 and noting what changed since then. The live version with links to every source is on [GradeKind](https://gradekind.com/school-days-by-state.html), together with a school-days-left counter and other grading tools for teachers.

## Files

| File | Content |
|---|---|
| `data/school-days-by-state-2026.csv` | `state, min_days, min_hours_per_year, rule, start_date_rule, changed_since_2023, law` |
| `data/school-days-by-state-2026.json` | same rows plus title, license and attribution |

## Reading the columns

- `min_days`: the minimum number of school days in the statute. Some states set only hours; then this cell says so.
- `min_hours_per_year`: minimum instructional hours (or minutes) per year, by grade band where the law splits them.
- `rule`: whether the state counts days, hours, or lets districts pick ("Days or hours").
- `start_date_rule`: states that fix when the year may start.
- `changed_since_2023`: what moved since the 2023 ECS list. "-" means no change found.
- `law`: the section to look up.

Two caveats from the research: Oregon is rewriting its instructional time rules after an April 2026 order from the governor; West Virginia's 900-hour rule starts on 1 July 2027.

## Quick use

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/RB9744/us-school-days-by-state/main/data/school-days-by-state-2026.csv')
df[df.rule.str.contains('hours', case=False)]
```

## Updates

Checked October 2026. Open an issue with a link to the statute if a state changes its rule.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit "GradeKind" with a link to https://gradekind.com/school-days-by-state.html.
