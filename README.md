Adjusted Fourth Down Efficiency (A4DE)

This project analyzes how NFL teams perform on **fourth-down plays**, introducing a custom metric called **Adjusted Fourth Down Efficiency (A4DE)**. A4DE combines **conversion rate** and **expected points added (EPA)** while adjusting for **defensive strength**, providing a clearer, more contextualized view of fourth-down performance.

---

## Project Highlights

- Developed a **new metric (A4DE)** that adjusts fourth-down EPA by defensive stop rates.
- Used **R** and the [`nflverse`](https://www.nflverse.com/) ecosystem to scrape and analyze NFL play-by-play data (2021–2024).
- Evaluated how fourth-down decision-making affects **team success**, including total wins and points.
- Compared **team-level** and **player-level** efficiency, with a spotlight on the **Philadelphia Eagles** and **Jalen Hurts**.
- Demonstrated **statistical significance** between A4DE and both points scored and games won using **linear regression**.

---

## Tools & Technologies

- **R + nflverse** (`nflreadr`, `nflfastR`, `dplyr`, `ggplot2`)
- **Markdown / RMarkdown** for reproducible reporting
- **Regression modeling** for impact analysis

---
## Methodology

1. **Data Sourcing:** Pulled play-by-play data using `nflverse` from 2021–2024.
2. **Filtering:** Focused exclusively on 4th-down plays and categorized outcomes as:
   - Go for it (pass/run)
   - Punt
   - Field Goal
3. **EPA + Conversion Rate Calculation**
4. **Defensive Adjustment:**
   - Calculated each defense’s stop rate: `1 - conversion rate`
   - Converted this to a percentile score
   - Adjusted EPA by `(1 + (1 - defensive percentile))`
5. **Final Metric:**  
   `A4DE = conversion_rate × adjusted_EPA`

---

## Key Findings

- The **Philadelphia Eagles** led the NFL in 4th-down efficiency with a 70.97% conversion rate in 2024, well above the league average of 57.11%.
- **A4DE** correlated positively with both **total wins** and **total points**, suggesting it captures high-leverage execution well.
- **Jalen Hurts** showed stable A4DE across seasons, with notable year-to-year trends tied to team and scheme changes.
- Teams like **Detroit** and **Washington** displayed aggressive 4th-down strategies that aligned with higher A4DE scores.
- Regression results show:
  - A one-point increase in A4DE ~ **324 more points/season**
  - A one-point increase in A4DE ~ **11 additional wins**

---
