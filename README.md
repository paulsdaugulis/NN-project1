# NN-project1
Multi-Layer Perceptron Project

[readme.md](https://github.com/user-attachments/files/24919869/readme.md)
\# Housing Price Prediction - Configurable MLP Experiments



This repository contains a Jupyter Notebook (`eda\_configured\_v2.ipynb`) designed to analyze housing market data and train Multi-Layer Perceptron (MLP) models to predict median house values.



The project features a \*\*centralized configuration system\*\* that allows users to define and run multiple experimental setups (e.g., varying learning rates, architectures, or preprocessing steps) seamlessly.



\## File Structure



\* \*\*`eda\_configured\_v2.ipynb`\*\*: The main notebook containing the configuration, data loading, exploratory data analysis (EDA), and experimental loops.

\* \*\*`houses.csv`\*\*: The dataset file (required for the notebook to run).



\## Key Features



\* \*\*Centralized Configuration\*\*: All settings—from model hyperparameters to data paths—are stored in a single `CONFIG` dictionary.

\* \*\*Experiment Management\*\*: The notebook is set up to iterate through a list of defined `experiments`. You can easily compare a "baseline" model against variants with different settings (e.g., `dropout`, `batchnorm`, `hidden\_sizes`) without rewriting code.

\* \*\*Exploratory Data Analysis\*\*: Includes built-in visualizations (histograms, boxplots) to inspect feature distributions and outliers before training.

\* \*\*Data Preprocessing\*\*: Handles train/test/validation splits, scaling (Standard or MinMax), and feature engineering (e.g., `log1p` transforms) based on the config.



\## Dependencies



To run this notebook, you will need the following Python libraries:



\* \*\*Jupyter\*\* (to run the `.ipynb` file)

\* \*\*Pandas\*\* (Data manipulation)

\* \*\*Matplotlib\*\* (Visualization)

\* \*\*NumPy\*\* (Numerical operations)

\* \*\*PyTorch\*\* (Deep Learning framework)



You can install the core requirements via pip:



```bash

pip install pandas matplotlib numpy torch
```
\## How to Use
Clone the repository:

```bash

git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
```

Launch Jupyter:

```bash
jupyter notebook
```

Open eda_configured_v2.ipynb.

Edit the Configuration (Optional): Locate the CONFIG cell at the top of the notebook. You can modify parameters such as:

"epochs": Number of training epochs.

"learning_rate": Optimizer step size.

"experiments": Add or remove dictionaries from this list to define new experimental runs.

Run all cells to execute the analysis and experiments.

\## Configuration Example
The notebook uses a configuration structure like this:

Python
CONFIG = {
    "model": {
        "learning_rate": 1e-3,
        "epochs": 60,
        "hidden_sizes": [64, 32],
        ...
    },
    "data": {
        "data_csv": "houses.csv",
        "target_col": "median_house_value",
        ...
    },
    "experiments": [
        {"name": "baseline", "model": {}, "train": {}},
        {"name": "high_dropout", "model": {"dropout": 0.5}, "train": {}},
        ...
    ]
}
\## Dataset
The model expects a CSV file (default: houses.csv) with the following columns (configurable):

median_income

housing_median_age

total_rooms

latitude

longitude

Target: median_house_value
