# Loan Approval Classification using Machine Learning

A machine-learning project that predicts whether a loan application is likely to be **approved or rejected** based on applicant and loan details. The project includes model experiments in Jupyter Notebook and an interactive web interface built with Streamlit.

> **Disclaimer:** This is an educational demonstration, not a real lending decision system. Predictions can be wrong and should not be used as the sole basis for financial decisions.

## Features

- Interactive Streamlit interface for entering applicant details.
- Uses a saved scikit-learn pipeline to make predictions.
- Inputs include age, gender, education, income, employment experience, home ownership, loan amount, loan purpose, interest rate, loan-to-income ratio, credit history length, credit score, and previous loan defaults.
- Jupyter Notebook for exploratory data analysis, model training, and comparison.
- Model performance results saved in `models_perf_dataset.csv`.

## Model comparison

The recorded test-set accuracies in `models_perf_dataset.csv` are:

| Model | Accuracy |
|---|---:|
| Random Forest | 91.89% |
| Support Vector Machine (SVM) | 91.37% |
| Decision Tree | 91.13% |
| Logistic Regression | 85.67% |
| Naive Bayes | 73.27% |

Random Forest has the highest accuracy in the recorded comparison. Accuracy alone does not show every type of prediction error; review precision, recall, the confusion matrix, and performance across different groups before using a model in a consequential setting.

## Project files

```text
loan-approval-classification/
├── app.py
├── best_model_pipeline.pkl
├── experiments(1).ipynb
├── loan_data.csv
├── models_perf_dataset.csv
├── logo (2).png
├── requirements.txt
└── README.md
```

Keep the filenames as shown, because `app.py` loads the model, dataset, and logo using these filenames.

## Requirements

- Python 3.10 or a compatible Python version
- pip
- The packages listed in `requirements.txt`

## Run locally

1. Download or clone this repository.
2. Open a terminal in the project folder.
3. (Recommended) Create and activate a virtual environment.

   **Windows (Command Prompt):**
   ```bat
   py -m venv .venv
   .venv\Scripts\activate
   ```

   **macOS/Linux:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

4. Install dependencies:

   ```bash
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

5. Start the Streamlit app:

   ```bash
   streamlit run app.py
   ```

6. Streamlit will show a local URL in the terminal (usually `http://localhost:8501`). Open it in your browser.

## How to use

1. Open the app.
2. Enter the applicant and loan details using the controls.
3. Click **Predict Loan Status**.
4. The app displays **Loan Approved** or **Loan Rejected** based on the saved model's prediction.

## Workflow

1. Load and inspect the loan dataset.
2. Explore the data and target distribution.
3. Split the data into training and testing sets.
4. Prepare numerical and categorical features in model pipelines.
5. Train and compare multiple classification models.
6. Save the best-performing pipeline.
7. Use the saved pipeline in the Streamlit interface.

## Notes

- The application reads `loan_data.csv` to populate some category choices, so that file must be present when running the app.
- The model file (`best_model_pipeline.pkl`) must be compatible with the installed scikit-learn version used to load it.
- Only load pickle files from sources you trust. Pickle files can execute code when loaded.
- Before publishing the dataset, confirm that you have permission to share it and that it contains no personal or confidential information.
- The current interface shows a class prediction, not a calibrated probability or explanation of the decision.

## Future improvements

- Add model evaluation with precision, recall, F1-score, and a confusion matrix.
- Add input validation and more realistic input ranges.
- Show a clear explanation that the result is a model estimate, not a lender's decision.
- Deploy the app using a hosting service that supports Streamlit.

## Author

Add your name, GitHub profile, and LinkedIn profile here.
