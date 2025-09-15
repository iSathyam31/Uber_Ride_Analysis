## Uber Ride Analysis

A lightweight project to explore and analyze Uber trip data using Python. It includes a reproducible Jupyter notebook for data cleaning, exploratory data analysis (EDA), and basic modeling/visualizations.

### Dataset
- **File**: `data/uber.csv`
- Place your Uber trips dataset at `data/uber.csv` (already included here).
- Typical columns may include pickup/dropoff timestamps, locations, trip distance, fare, and rider/driver identifiers. Adjust the notebook if your schema differs.

### Project structure
- `notebooks/analysis.ipynb`: Main analysis notebook
- `data/uber.csv`: Source dataset
- `requirements.txt`: Minimal dependency list
- `pyproject.toml` and `uv.lock`: Project metadata and locked deps (for `uv`)

### Requirements
- Python 3.12+
- One of:
  - `uv` (recommended) — fast Python package manager
  - or classic `pip`

### Quick start

#### Option A: Using uv (recommended)
```bash
# Install uv if needed (see https://docs.astral.sh/uv/)
# On Windows (PowerShell):
irm https://astral.sh/uv/install.ps1 | iex

# From the project root
uv sync  # creates a .venv and installs deps from pyproject/uv.lock

# Activate the environment
. .venv\Scripts\Activate.ps1
```

#### Option B: Using pip
```bash
# Create and activate a virtual environment (Windows PowerShell)
python -m venv .venv
. .venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt
```

### Run the analysis notebook
```bash
# From the activated virtual environment
python -m ipykernel install --user --name uber-data-analytics --display-name "Python (uber-data-analytics)"
python -m jupyter notebook
```
Then open `notebooks/analysis.ipynb` and select the "Python (uber-data-analytics)" kernel. If prompted to trust the notebook, accept.

### What you can expect in the notebook
- Data loading and sanity checks
- Cleaning and feature engineering (dates, durations, geospatial basics)
- EDA with `pandas`, `seaborn`, and `matplotlib`
- Simple baselines or aggregations (e.g., demand by hour/day, trip distance distributions)

### Tips
- If `ipywidgets` controls don’t display, enable widgets in Jupyter Lab: `jupyter labextension install @jupyter-widgets/jupyterlab-manager` (not required for classic Notebook).
- For large `uber.csv`, consider chunked reading with `pandas.read_csv(..., chunksize=...)` and downcasting dtypes.
- Keep raw data read-only; save derived tables/figures under a new `outputs/` folder if needed.

### License
This project is provided for educational purposes. Add a license if you plan to distribute.

### Acknowledgments
Uber trip data and schema references are credited to their respective sources. This project uses open-source libraries: NumPy, pandas, matplotlib, seaborn, scikit-learn, ipykernel, and ipywidgets.
