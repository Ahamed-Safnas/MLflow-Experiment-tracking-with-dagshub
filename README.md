# MLflow Experiment Tracking with DagsHub

## Overview

This project demonstrates how to train a machine learning model using **scikit-learn** and track experiments using **MLflow**, with **DagsHub** as a remote tracking server.

The goal is to:

* Train an ElasticNet regression model
* Log parameters, metrics, and models
* Link each experiment to its **exact GitHub commit** for reproducibility

---

## Why this project exists

In machine learning, running experiments without tracking leads to:

* Lost results
* No reproducibility
* No clear comparison between models

This project solves that by combining:

* **GitHub** → code versioning
* **MLflow** → experiment tracking
* **DagsHub** → centralized storage + visualization

---

## Tech Stack

* Python
* scikit-learn
* MLflow
* DagsHub
* Pandas, NumPy

---

## Dataset

The project uses the **Wine Quality (Red)** dataset provided by MLflow:

* Source: UCI Machine Learning Repository
* Target variable: `quality`
* Task: Regression

Dataset is loaded directly from a public URL.

---

## Project Structure

```
.
├── main.py          # Training and MLflow tracking script
├── requirements.txt # Project dependencies
├── README.md        # Project documentation
```

---

## How the system works (simple flow)

1. Load the dataset
2. Split into training and test sets
3. Train an ElasticNet regression model
4. Evaluate model performance (RMSE, MAE, R²)
5. Log:

   * Hyperparameters
   * Metrics
   * Trained model
6. Store all experiment data in DagsHub via MLflow
7. Link each run to the GitHub commit that produced it

---

## Why MLflow is used

MLflow is used to:

* Track hyperparameters (`alpha`, `l1_ratio`)
* Track evaluation metrics
* Store trained models
* Compare multiple experiment runs

Without MLflow, results are only printed to the terminal and lost.

---

## Why DagsHub is used

DagsHub provides:

* A **remote MLflow tracking server**
* Centralized experiment storage
* Integration with GitHub for reproducibility

This allows experiments to be:

* Viewed in a browser
* Compared across runs
* Shared with teammates or supervisors

---

## Why GitHub is connected to DagsHub

Connecting GitHub ensures:

* Each MLflow run is linked to an **exact code version**
* Results are reproducible
* Changes in code can be traced to changes in performance

Without this connection, experiments cannot be reliably reproduced.

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

---

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate      # Windows
```

---

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Commit and push code (important)

MLflow can only track Git commits if the code is committed.

```bash
git add .
git commit -m "Initial MLflow experiment setup"
git push origin main
```

---

## Running the Project

You can pass hyperparameters from the command line:

```bash
python main.py 0.5 0.5
```

Where:

* `alpha` → regularization strength
* `l1_ratio` → balance between L1 and L2 regularization

If no arguments are provided, default values are used.

---

## Viewing Experiments

1. Open your DagsHub repository
2. Go to **Experiments → MLflow**
3. Select a run to view:

   * Parameters
   * Metrics
   * Git commit
   * Logged model

---

## Key Learning Outcomes

* How to track ML experiments properly
* How to link results to code versions
* How to use MLflow with a remote tracking server
* Why reproducibility matters in machine learning projects

---

## Notes

* This project is for **learning and demonstration**
* It is not production-ready
* No hyperparameter tuning or cross-validation is performed

---

## Author

Safnas

---


