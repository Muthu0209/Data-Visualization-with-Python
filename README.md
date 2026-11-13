# Data-Visualization-with-Python
Hands-on practice notebook exploring core data visualization techniques in Python using Matplotlib and Seaborn — histograms, boxplots, bar graphs, line plots, scatterplots, pair plots, and heatmaps — applied to an automobile dataset to analyze distributions, relationships, and trends across numerical and categorical variables. practiced as part of the Data Analytics Essentials program (Great Learning)


## Dataset

`Automobile (1).csv` — 201 vehicles, 26 attributes, including:

| Type | Columns (examples) |
|---|---|
| Categorical | `make`, `fuel_type`, `body_style`, `drive_wheels`, `engine_type`, `number_of_doors` |
| Numerical | `price`, `horsepower`, `curb_weight`, `engine_size`, `wheel_base`, `bore`, `stroke`, `city_mpg`, `highway_mpg` |

**Quick facts from the data**
- Car prices range from 5,118 to 45,400.
- Curb weight ranges from 1,488 to 4,066.
- Toyota is the most common make.

Line plots also use Seaborn's built-in `flights` and `fmri` example datasets.

## What's Covered

| Plot | Seaborn function | What it shows | Used on |
|---|---|---|---|
| Histogram | `histplot()` | Distribution of a numeric variable (bins, binwidth, KDE, skewness) | `price`, `curb_weight`, `horsepower`, `bore` |
| Boxplot | `boxplot()` | Five-number summary, skewness, group comparison | `price` by `body_style`, `horsepower` |
| Bar graph | `countplot()` | Counts per category, with `hue` for sub-groups | `body_style`, `make`, `engine_type` by `fuel_type` |
| Line plot | `lineplot()` | Trends, confidence intervals, `hue`/`style`/markers | `flights`, `fmri` |
| Scatterplot | `scatterplot()` | Relationship between two numeric variables | `engine_size` vs `horsepower`, `curb_weight` vs `engine_size`, `bore` vs `stroke` |
| Pair plot | `pairplot()` | All pairwise relationships (`hue`, `vars`, `corner`) | price, weight, engine size, wheel base |
| Heatmap | `heatmap()` | Correlation matrix (`annot`, `cmap`) | `wheel_base`, `curb_weight`, `engine_size`, `price` |

## Key Takeaways

- **Price is right-skewed** — most cars are low-priced, with a few expensive outliers.
- **Boxplots vs. histograms:** boxplots compare groups well but can hide multimodality (e.g. `bore`), which a histogram reveals.
- **Engine size and horsepower** are positively correlated; **bore and stroke** show no clear correlation.
- Too many bins flatten the KDE curve; the notebook also shows a rule-of-thumb for choosing bin width.
- Large category axes (like `make`) need a bigger figure and rotated tick labels to stay readable.

## Tech Stack

- Python 3
- pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

## Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/Muthu0209/Data-Visualization-with-Python.git
cd Data-Visualization-with-Python

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook PythonVisualization.ipynb
```

**Note:** the notebook was written in Google Colab and loads the CSV from Google Drive. To run it locally, change the load line to:

```python
df = pd.read_csv('Automobile_1.csv')
```

and skip the `drive.mount(...)` cells.

## Repository Structure

```
├── PythonVisualization.ipynb   # Main notebook
├── Automobile (1).csv            # Dataset
└── README.md
```

## Author

**Muthulakshmi Viswanathan** — Data Analyst, Toronto, Canada
[GitHub](https://github.com/Muthu0209)
