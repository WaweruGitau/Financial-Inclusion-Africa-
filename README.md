# Financial Inclusion in Africa — Bank Account Prediction

A classification model predicting whether an individual is likely to have or
use a bank account, built on the [Zindi Financial Inclusion in
Africa](https://zindi.africa/competitions/financial-inclusion-in-africa)
survey dataset covering respondents across Kenya, Rwanda, Tanzania, and
Uganda.

## Approach

**Exploratory data analysis**
- Distribution and quartiles of respondent age and household size
- Target variable (`bank_account`) class balance

**Preprocessing**
- One-hot encoding of categorical features (`relationship_with_head`,
  `marital_status`, `education_level`, `job_type`, `country`)
- Correlation-based feature pruning — dropped features with near-zero
  correlation to the target
- Min-max scaling of features into a `[0, 1]` range

**Modeling**
- Logistic Regression, trained on a stratified train/validation split
- Evaluated with accuracy score and a confusion matrix
- Final predictions generated on the competition test set and written out
  as a submission CSV

## Tech Stack

- **Python**
- **pandas** / **NumPy** — data wrangling
- **scikit-learn** — preprocessing, Logistic Regression, evaluation metrics
- **Seaborn** / **Matplotlib** — exploratory visualizations
- **Jupyter Notebook**

## Running it

1. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn seaborn matplotlib jupyter
   ```
2. Download the dataset from the [Zindi competition
   page](https://zindi.africa/competitions/financial-inclusion-in-africa)
   (`Train.csv`, `Test.csv`, `SampleSubmission.csv`,
   `VariableDefinitions.csv`) and update the working directory path in the
   notebook's second cell to point at your local copy.
3. Open `Financial Inclusion in Africa(Prediction).ipynb` in Jupyter and run
   all cells.

## Project Structure

```
.
└── Financial Inclusion in Africa(Prediction).ipynb   # EDA, preprocessing, model, submission
```
