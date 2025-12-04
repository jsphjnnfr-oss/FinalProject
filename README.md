# Quarterback Anticipation and Decision Efficiency Using NFL Tracking Data

## Overview

This repository contains the research project exploring quarterback anticipation in the NFL using player tracking data. The study quantifies the timing between a quarterback's throw release and the receiver’s route break, analyzing how anticipation affects play outcomes such as completion probability, yards gained, and Expected Points Added (EPA).

## Motivation

Quarterback anticipation is a critical skill in football, yet it has rarely been measured quantitatively. This project aims to provide a data-driven metric to evaluate decision efficiency, cognitive processing, and timing precision for quarterbacks.

## Datasets

* **NFL Big Data Bowl Tracking Data (2018–2023)**: Frame-by-frame positions of all players and the ball.
* **NFLFastR Play-by-Play Data**: Game outcomes, EPA, play types, and other contextual features.
* **Pro-Football-Reference**: Player identifiers and QB statistics.
* **Optional**: NFL Next Gen Stats summaries for validation.

> **Note:** Datasets are publicly available; links and usage instructions are provided in the repository.

## Project Structure

```
├── data/             # Raw and processed data (tracking & play-by-play)
├── notebooks/        # Jupyter notebooks for analysis and visualization
├── scripts/          # Python scripts for data processing and modeling
├── figures/          # Plots and charts generated during analysis
├── results/          # Regression and model results
├── NFL_QB_Anticipation_Paper.docx  # Full research paper
└── README.md         # Project description
```

## Methodology

1. **Data Preprocessing**: Filter pass plays and extract frames for QB throw release and receiver route break.
2. **Anticipation Metric**: Compute Anticipation Time (AT) = `t_throw - t_route_break`.
3. **Merging**: Combine AT with play-level outcomes (EPA, completion, turnovers).
4. **Analysis**: Logistic regression for completion probability, linear regression for EPA, and exploratory visualizations.
5. **Validation**: Compare results across quarterbacks and play contexts.

## Key Findings

* Moderate anticipation (~0.2–0.45 seconds before route break) improves completion probability and EPA.
* Extremely early throws increase interception risk.
* Elite quarterbacks display lower variance in anticipation timing.

## Requirements

* Python 3.9+
* Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, shapely, scipy

Install dependencies via pip:

```bash
pip install -r requirements.txt
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/yourusername/nfl-qb-anticipation.git
```

2. Process and analyze the data:

```bash
python scripts/process_tracking_data.py
```

3. Explore notebooks for visualization and modeling:

```bash
jupyter notebook notebooks/Analysis.ipynb
```

## References

* Burke, B. (2019). NFLFastR: Open-source play-by-play data for the NFL.
* Next Gen Stats. (2018–2023). NFL Player Tracking Data.
* Yurko, R., Ventura, S., & Horowitz, M. (2020). nflWAR: A reproducible framework for evaluating NFL players.
* Sauer, S. (2021). Spatial analysis in American football using tracking data. Journal of Sports Analytics.
* Ploetz, T., & Dwyer, D. (2020). Machine learning applications in player tracking sports analytics.

## License

This project is licensed under the MIT License.
