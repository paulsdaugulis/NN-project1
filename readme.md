# Housing Price Prediction – Configurable MLP Experiments

This repository contains a Jupyter Notebook (`eda_configured_v2.ipynb`) for analyzing housing market data and training **Multi-Layer Perceptron (MLP)** models to predict median house values.

The project is built around a **centralized configuration system** that makes it easy to define, run, and compare multiple experimental setups (e.g. different learning rates, network architectures, or preprocessing strategies) without duplicating code.

---

## File Structure

- **`eda_configured_v2.ipynb`** – Main notebook containing configuration, data loading, exploratory data analysis (EDA), model definition, training loops, and experiment comparisons.
- **`houses.csv`** – Dataset file required to run the notebook.

---

## Key Features

- **Centralized Configuration**  
  All settings (model hyperparameters, training options, preprocessing choices, and paths) are defined in a single `CONFIG` dictionary.

- **Experiment Management**  
  The notebook iterates over a list of experiments, making it simple to compare a baseline model with variants that adjust parameters such as `dropout`, `batchnorm`, or `hidden_sizes`.

- **Exploratory Data Analysis (EDA)**  
  Built-in visualizations (histograms, boxplots) help inspect feature distributions and identify outliers before training.

- **Data Preprocessing**  
  Supports train/validation/test splits, feature scaling (StandardScaler or MinMaxScaler), and optional feature transformations (e.g. `log1p`) controlled entirely through configuration.

---

## Dependencies

To run the notebook, you will need the following Python libraries:

- **Jupyter** – Run the `.ipynb` notebook
- **Pandas** – Data manipulation
- **NumPy** – Numerical operations
- **Matplotlib** – Visualization
- **PyTorch** – Deep learning framework

Install the core dependencies with:

```bash
pip install pandas numpy matplotlib torch
```

---

## How to Use

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

3. **Open the notebook**  
   Open `eda_configured_v2.ipynb` in your browser.

4. **(Optional) Edit the Configuration**  
   At the top of the notebook, locate the `CONFIG` dictionary. Common options include:
   - `epochs` – Number of training epochs
   - `learning_rate` – Optimizer step size
   - `hidden_sizes` – MLP architecture
   - `experiments` – List of experiment variants to run

5. **Run all cells** to execute the analysis and training experiments.

---

## Configuration Example

The notebook uses a configuration structure similar to the following:

```python
CONFIG = {
    "model": {
        "learning_rate": 1e-3,
        "epochs": 60,
        "hidden_sizes": [64, 32]
    },
    "data": {
        "data_csv": "houses.csv",
        "target_col": "median_house_value"
    },
    "experiments": [
        {"name": "baseline", "model": {}, "train": {}},
        {"name": "high_dropout", "model": {"dropout": 0.5}, "train": {}}
    ]
}
```

---

## Dataset

By default, the notebook expects a CSV file named `houses.csv` containing the following columns (all configurable):

- `median_income`
- `housing_median_age`
- `total_rooms`
- `latitude`
- `longitude`

**Target variable:**
- `median_house_value`

---

## Notes

- The code is designed for experimentation and learning rather than production deployment.
- Additional features or columns can be added by updating the configuration and preprocessing sections of the notebook.

