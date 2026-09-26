# FIFA 19 Player Statistics Analysis

A statistical deep-dive into 18,000+ professional footballers from the FIFA 19
dataset — going beyond basic EDA into formal hypothesis testing to separate
real patterns from statistical noise.

## What this project does

Most FIFA-dataset projects stop at charts and summary stats. This one asks
"is that difference actually significant, or just noise?" for every claim —
using proper normality checks, t-tests, ANOVA, correlation tests, and
chi-square tests, then interprets what the results mean for scouting.

## Key questions answered

- Does preferred foot affect a player's Overall rating?
- Are Forwards really rated higher than Defenders?
- Which position group stands out — and is it statistically real?
- What actually predicts Overall rating: technical skill, or physicality?
- Does Potential decline with age?
- Is skill level or preferred foot linked to playing position?

## Highlights from the analysis

- **18,147 players** analyzed across 4 position groups (GK, Defender,
  Midfielder, Forward)
- Goalkeepers rate significantly lower in Overall than all outfield
  positions (ANOVA + Tukey post-hoc, p < 0.001) — but Defenders,
  Midfielders, and Forwards don't meaningfully differ from each other
- `Potential` and passing/ball-control metrics predict Overall far better
  than raw physical attributes like Strength
- Preferred foot and skill level are both statistically linked to playing
  position (chi-square, p < 0.001)

## Methodology

1. **Data cleaning** — parsed currency-formatted value/wage fields,
   simplified 15+ raw positions into 4 position groups
2. **Exploratory analysis** — distribution plots, boxplots by position,
   scatter plots with trend lines
3. **Normality testing** — Shapiro-Wilk + Q-Q plots to justify test choice
   (parametric vs. non-parametric)
4. **Hypothesis testing** — t-tests, one-way ANOVA with Tukey HSD post-hoc
5. **Correlation analysis** — Pearson/Spearman correlation matrix and
   significance testing
6. **Categorical association** — chi-square tests of independence
7. **Synthesis** — consolidated results table and a plain-language
   scouting brief

## Tech stack

`Python` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SciPy` ·
`statsmodels` · `Jupyter Notebook`

## Dataset

FIFA 19 complete player dataset (~18K players, 89 attributes),
sourced from [Kaggle / original source link].

## Running it

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels
jupyter notebook my_fifa_challenge.ipynb
```