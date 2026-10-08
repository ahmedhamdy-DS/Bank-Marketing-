# Bank Marketing: Term Deposit Prediction

University group project. We analyze direct marketing campaigns (phone calls) of a Portuguese bank and build models to predict whether a client will subscribe to a term deposit.

## Team

| Name | GitHub |
|------|--------|
| Ahmed Hamdy | [@ahmedhamdy-DS](https://github.com/ahmedhamdy-DS) |
| Member 2 | @username |
| Member 3 | @username |

## Dataset

- **Name:** Bank Marketing (UCI Machine Learning Repository)
- **Task:** Binary classification
- **Instances:** 45,211
- **Features:** 16 (categorical and integer)
- **Target:** `y` (has the client subscribed a term deposit? yes / no)
- **Missing values:** none officially, but some columns use `"unknown"` as a category
- **Paper:** Moro, Cortez, Rita (2014), *A data-driven approach to predict the success of bank telemarketing*

### Features

| Group | Columns |
|-------|---------|
| Client data | `age`, `job`, `marital`, `education`, `default`, `balance`, `housing`, `loan` |
| Last contact of this campaign | `contact`, `day`, `month`, `duration` |
| Other | `campaign`, `pdays`, `previous`, `poutcome` |

Notes:
- `pdays = -1` means the client was not contacted in a previous campaign.
- `duration` is only known after the call ends, so it should not be used in a realistic prediction model (data leakage). Try the models with and without it.
- The target is imbalanced (far more "no" than "yes"), so use F1, recall, and ROC-AUC, not accuracy only.

### Files

The dataset comes as zip files. Unzip and put the CSV files inside the `data/` folder:

- `bank-full.csv`: all examples, 17 columns (16 features + target)
- `bank.csv`: 10% random sample, same columns, good for quick tests

Load it like this (the separator is `;`):

```python
import pandas as pd
df = pd.read_csv("data/bank-full.csv", sep=";")
```

If the files are too big for the repo, we keep them out of Git and share them on Drive: add link here.

## Project Structure

```
.
├── data/              # dataset files
├── notebooks/         # Jupyter notebooks (EDA, preprocessing, modeling)
├── requirements.txt   # project dependencies
└── README.md
```

## Setup

1. Clone the repo:
   ```
   git clone <repo-url>
   cd <repo-name>
   ```
2. (Optional) Create a virtual environment:
   ```
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # Mac / Linux
   ```
3. Install the libraries:
   ```
   pip install -r requirements.txt
   ```
4. Start Jupyter:
   ```
   jupyter notebook
   ```

## Workflow

1. Pull the latest changes: `git checkout main` then `git pull`
2. Create your own branch: `git checkout -b yourname-task`
3. Work, then commit and push:
   ```
   git add .
   git commit -m "describe what you did"
   git push origin yourname-task
   ```
4. Open a Pull Request and ask a teammate to review it before merging.

## Tasks

- [ ] Data cleaning (handle `"unknown"` values, check duplicates)
- [ ] Exploratory data analysis (EDA)
- [ ] Preprocessing (encoding, scaling, handle class imbalance)
- [ ] Modeling (Logistic Regression, Random Forest, etc.)
- [ ] Evaluation
- [ ] Final report / presentation

## Results

Add the main findings, metrics, and charts here once the work is done.