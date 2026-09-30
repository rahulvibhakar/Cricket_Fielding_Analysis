# Cricket Fielding Analysis

A Streamlit-based cricket analytics dashboard for evaluating fielding performance during matches. The app helps you record fielding actions, calculate player impact using configurable weights, compare players, and visualize fielding trends across matches, venues, innings, and positions.

## Overview

This project is designed for coaches, analysts, and cricket enthusiasts who want to quantify the value a fielder adds beyond batting and bowling. It tracks important fielding actions like:

- clean picks
- good throws
- catches
- dropped catches
- stumpings
- run outs
- missed run outs
- direct hits
- runs saved or conceded

These actions are aggregated into a player-level performance score that can be compared and visualized across different match conditions.

## Features

- Data collection form for fielding entries
- Match, team, innings, venue, and position filters
- Weighted fielding performance scoring
- Player rankings with detailed contribution breakdowns
- Visual dashboards for:
  - player performance comparison
  - position analysis
  - over-by-over analysis
  - heatmaps
- Adjustable performance weights with presets
- CSV import/export for fielding data and metrics
- Manual backup and restore of saved data

## Project Structure

```text
.
├── cricket_analysis.py      # Main Streamlit app
├── fielding_data.csv        # Sample fielding dataset
├── IPL sample data.csv      # Additional sample dataset
├── cricket_data/            # Runtime folder created by the app
│   ├── fielding_data.csv
│   ├── weights.json
│   └── backups/
├── README.md
└── .gitignore
```

## Tech Stack

- Python 3
- Streamlit
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Installation

1. Clone the repository.
2. Create and activate a virtual environment (recommended):

```bash
python -m venv .venv
.\.venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install streamlit pandas numpy matplotlib seaborn
```

## Running the App

From the project root, run:

```bash
streamlit run cricket_analysis.py
```

Then open the local URL shown in the terminal (usually `http://localhost:8501`).

## How It Works

### 1. Data Collection
Use the “Data Collection” page to add fielding entries such as:

- match number
- innings
- team
- player name
- ball count
- fielding position
- short description
- pick/throw outcome
- runs saved or conceded
- venue

### 2. Performance Analysis
Use filters to analyze a specific match, team, innings, or venue. The app calculates a performance score based on weighted fielding actions and displays summary metrics by player.

### 3. Visualization
The app includes several analysis views:

- player vs player comparison
- position-wise trend analysis
- over-by-over breakdown
- performance heatmaps

### 4. Settings
Adjust fielding weights to match different evaluation preferences. The app also includes preset configurations such as:

- Standard T20 weights
- Balanced weights

## Scoring Formula

```text
PS = (CP × WCP) + (GT × WGT) + (C × WC) + (DC × WDC) + (ST × WST) + (RO × WRO) + (MRO × WMRO) + (DH × WDH) + RS
```

Where:

- CP = Clean Picks
- GT = Good Throws
- C = Catches
- DC = Dropped Catches
- ST = Stumpings
- RO = Run Outs
- MRO = Missed Run Outs
- DH = Direct Hits
- RS = Runs Saved

## Sample Data

The repository includes sample CSV files that can be imported into the app or used as reference datasets for experimentation.

## Notes

- The app creates a `cricket_data` directory on first run to store saved CSV and JSON files.
- The scoring logic is configurable from the settings panel.
- Data can be exported as CSV for analysis outside the app.
- Manual backups are supported for fielding data and weights.

## Future Improvements

Possible extensions include:

- team-level fielding dashboards
- long-term player trend analysis
- predictive modeling for fielding value
- database-backed storage
- integration with match video or event logs

## License

This project is provided for educational and analytical use. Add an appropriate license if you plan to distribute or share it publicly.

## Summary

This project is a practical starter for cricket fielding analysis and dashboarding. It is suitable for learning, demos, coaching analysis, and custom fielding evaluation workflows.
```
