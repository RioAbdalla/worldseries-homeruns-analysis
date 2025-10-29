# World Series Home Runs Win Probability Analysis

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

This project analyzes the relationship between home run differential and win probability in World Series games from 2017 to 2024. The analysis demonstrates that home runs have a statistically significant impact on game outcomes, with each additional home run increasing the odds of winning by approximately 77%.

## Key Findings

- **Odds Ratio**: 1.773 per +1 home run differential
- **Statistical Significance**: p = 0.012 (99% confidence)
- **Win Probability Impact**: ~14% increase per additional home run
- **Interpretation**: Hitting one more homer than your opponent nearly doubles your chances of winning

## Dataset

The analysis uses World Series game data from 2017-2024, including:
- Year and Game number
- Team matchups
- Runs scored (Team_R, Opp_R)
- Home runs hit (Team_HR, Opp_HR)
- Home run differential (HR_diff)
- Game outcome (Win/Loss)

**Sample Size**: 46 games across 4 World Series (2017, 2018, 2020, 2024)

## Methodology

### Statistical Analysis
- **Model**: Logistic Regression (`Win ~ HR_diff`)
- **Framework**: `statsmodels` library
- **Coefficient**: 0.573 (SE = 0.228, z = 2.52)
- **Confidence Interval**: [0.127, 1.019] at 95% level

### Visualization
The project generates a publication-ready scatter plot showing:
- Observed win rates by home run differential (bubble size = sample size)
- Logistic regression fit curve
- Individual game data points (rug plot)

## Installation

### Requirements
```bash
pip install numpy pandas matplotlib statsmodels
```

For Google Colab (included in notebook):
```python
# Uncomment if statsmodels not installed
# !pip install statsmodels==0.14.0 --quiet
```

## Usage

### Running the Analysis

1. **Clone the repository**:
```bash
git clone https://github.com/yourusername/worldseries-homeruns-analysis.git
cd worldseries-homeruns-analysis
```

2. **Prepare your data**:
   - Ensure your CSV file follows the format: `Year, Game, Team, Opponent, Team_R, Opp_R, Team_HR, Opp_HR, HR_diff, Win`

3. **Run the notebook**:
   - Open `worldseries_homeruns_winprob_analysis.ipynb` in Jupyter/Colab
   - Upload your CSV when prompted
   - Execute all cells

### Output Files
The analysis generates:
- `ws_hrdiff_winprob_hero.png` - High-resolution visualization (150 DPI)
- `ws_hrdiff_winrate_summary.csv` - Summary statistics by HR differential

## Project Structure

```
worldseries-homeruns-analysis/
│
├── worldseries_homeruns_winprob_analysis.ipynb  # Main analysis notebook
├── World_Series_Combined_Summary__2017_2024_.csv # Dataset
├── ws_hrdiff_winrate_summary.csv                 # Summary output
├── ws_hrdiff_winprob_hero.png                    # Visualization
└── README.md                                      # This file
```

## Results Interpretation

### Win Probability by Home Run Differential

| HR_diff | Win Rate | Sample Size |
|---------|----------|-------------|
| -3      | 25%      | 4           |
| -2      | 25%      | 4           |
| -1      | 22%      | 9           |
| 0       | 50%      | 12          |
| +1      | 78%      | 9           |
| +2      | 75%      | 4           |
| +3      | 75%      | 4           |

### Statistical Model Output

```
Coefficient (HR_diff): 0.573
Standard Error: 0.228
z-statistic: 2.516
p-value: 0.012
Odds Ratio: 1.773 (77.3% increase per +1 HR)
```

## Visualization

![World Series Win Probability vs Home Run Difference](ws_hrdiff_winprob_hero.png)

The plot shows:
- **Blue circles**: Observed win rates (size proportional to sample size)
- **Blue curve**: Logistic regression fit
- **Orange tick marks**: Individual game outcomes

## Limitations & Future Work

### Current Limitations
- Small sample size for extreme HR differentials (±2, ±3)
- Limited to 4 World Series (2017, 2018, 2020, 2024)
- Does not account for other factors (pitching, fielding, etc.)

### Potential Extensions
- Include regular season data for larger sample size
- Add control variables (team quality, home field advantage)
- Analyze timing of home runs (inning-by-inning impact)
- Compare with other offensive metrics (batting average, OPS)

## Technologies Used

- **Python 3.7+**
- **NumPy**: Numerical computations
- **Pandas**: Data manipulation
- **Matplotlib**: Visualization
- **Statsmodels**: Statistical modeling
- **Google Colab**: Development environment

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Data sourced from [Baseball Reference](https://www.baseball-reference.com/)
- Inspired by a conversation with Evan about World Series strategy
- Special thanks to the baseball analytics community

## Contact

- **Author**: [Your Name]
- **LinkedIn**: [Your LinkedIn Profile]
- **Email**: [your.email@example.com]
- **Project Link**: [https://github.com/yourusername/worldseries-homeruns-analysis](https://github.com/yourusername/worldseries-homeruns-analysis)

## Citation

If you use this analysis in your research or writing, please cite:

```
[Your Name]. (2024). World Series Home Runs Win Probability Analysis. 
GitHub repository: https://github.com/yourusername/worldseries-homeruns-analysis
```

---

**Tags**: `#DataScience` `#BaseballAnalytics` `#MLB` `#SportsAnalytics` `#LogisticRegression` `#Python` `#DataVisualization`