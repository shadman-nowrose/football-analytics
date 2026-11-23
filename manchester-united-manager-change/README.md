# Manager change analysis: Manchester United, 2026-27

Manchester United sacked Michael Carrick on 12 November 2026 after 10 league games and appointed Mauricio Pochettino. This project looks at whether the team's numbers change under the new manager, and by how much.

## Method

- **Baseline:** Carrick's 10 Premier League games this season (22 Aug to 8 Nov), saved as `carrick_era_clean.csv` and not edited afterwards.
- **Comparison:** Pochettino's games, added to a separate file after each match and cleaned the same way.
- **Metrics:** goals, shots, shots on target, corners, fouls and points, with home and away splits. Every figure is from United's side, shown as "for" and "against".

## Carrick baseline

| | |
|---|---|
| Record | 1 win, 5 draws, 4 defeats (8 points) |
| Goals for / against | 14 / 19 |
| Shots per game for / against | 19.3 / 11.8 |
| Shots on target per game for / against | 5.4 / 5.1 |

United had more shots than their opponents in 7 of the 10 games but still conceded more than they scored. Shot counts can't say whether that comes from finishing, shot quality or defensive mistakes. Expected goals (xG) would help separate them, and it's the next thing I want to add.

![Shots for vs against](shots_for_vs_against.png)
![Cumulative goals](cumulative_goals.png)

## Limitations

- Ten games is a small sample, and the Pochettino sample will be small for a while. Early differences may just be noise.
- No xG yet. My first attempt at an xG source failed, so I'm looking for another one.
- Fixture difficulty isn't adjusted for.

## Data

Match results and shot counts from football-data.co.uk.

## Files

- `01_data_check.ipynb`: loading, cleaning, charts
- `carrick_era_clean.csv`: cleaned baseline data
- `shots_for_vs_against.png`, `cumulative_goals.png`: charts

## Status

Baseline complete. Pochettino's games will be added once their data is available.

## Findings so far

- Across the 10 Carrick games, 43% of shots United conceded were on target, against 31% across the league. The pattern holds in 9 of the 10 games, so it isn't one bad match.
- United's own finishing (0.26 goals per shot on target against 0.32 for the league) is lower, but with 54 shots on target the gap is within what chance could produce.
- Tentative reading: the issue looks more like the quality of chances conceded than wasteful finishing. Shot counts can't confirm this, and xG would help.

## Benchmark: Real Madrid under Mourinho

Madrid's 2026-27 season so far (13 La Liga and 4 Champions League games) sits alongside United's Carrick era (10 league and 4 Champions League games).

- Against their own league averages, Madrid are better on attack (shot accuracy 0.41 vs 0.34, goals per shot on target 0.35 vs 0.31) and much lower on opponents' conversion (0.21 vs 0.31).
- United were below average on attack and well above average on both opponent measures.
- In the Champions League, both teams' numbers swing a lot from their league figures. With four games each, I don't read much into that.

Caveats: small samples, different opposition, and league and Champions League data come from different providers. Madrid's Champions League shot ratios exclude the Inter game, whose shot figures didn't add up.