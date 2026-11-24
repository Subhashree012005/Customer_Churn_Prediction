# Customer Churn Prediction

A machine learning project that predicts which telecom customers are likely to leave, so a company can offer them a deal before they go. It also turns the model output into a simple business plan: who to target first, and how much monthly revenue is at risk.

## Business Problem

Keeping an existing customer costs less than finding a new one. If the company can spot customers who are about to leave, it can act early with offers or better plans.

**Goal:** predict customer churn, find the main reasons for it, and recommend which customers to target first.

## Dataset

- **Name:** Telco Customer Churn (IBM sample data, also on Kaggle)
- **Size:** about 7,000 customers, 20 columns
- **Target:** `Churn` (Yes or No)
- **Features:** contract type, tenure, monthly charges, internet service, payment method, and more

## Approach

1. **Load and explore** the data and find the overall churn rate.
2. **Clean** the data: fix `TotalCharges` (text to number), drop `customerID`, convert the target to 1 and 0.
3. **Prepare features** with one-hot encoding.
4. **Split** into train (80%) and test (20%) with `stratify` to keep the churn ratio the same.
5. **Train two models:** Logistic Regression and Random Forest, both with `class_weight="balanced"` because only about 1 in 4 customers churn.
6. **Evaluate** with precision, recall, F1, ROC-AUC and a confusion matrix, not accuracy alone.
7. **Tune the threshold** to catch more churners (higher recall).
8. **Business step:** group customers into High, Medium and Low risk, and find high-risk, high-value customers.

## Results

> Replace the values below with your own results after running the notebook.

| Model | Precision (Churned) | Recall (Churned) | ROC-AUC |
|---|---|---|---|
| Logistic Regression | [your value] | [your value] | [your value] |
| Random Forest | [your value] | [your value] | [your value] |

**Churn rate in the data:** [your value]%

**Top factors behind churn:** [for example: contract type, tenure, monthly charges. Use your own chart.]

**Customers to target first (high risk + high value):** [your number], with about [your number] monthly revenue at risk.

## Key Insights

- [Write 2 or 3 findings from your own results, for example: month-to-month customers churn much more than customers on long contracts.]
- Accuracy can be misleading on imbalanced data, so recall for churners was the main metric. Missing a customer who leaves costs more than a false alarm.

## Business Recommendation

1. Offer discounts or contract upgrades first to **high-risk, high-value** customers.
2. Encourage month-to-month customers to move to a 1-year plan.
3. Run an **A/B test**: send the offer to half of the targeted customers and compare churn with the other half.

## Limitations

- The data comes from one company and is not recent, so results may not apply everywhere.
- The model shows who is likely to leave, not why. Customer feedback is also needed.
- Only basic models were tried, with no heavy tuning.

## Tech Stack

Python, Pandas, NumPy, Matplotlib, scikit-learn, Google Colab

## How to Run

1. Open [Google Colab](https://colab.research.google.com).
2. Upload `Customer_Churn_Prediction.ipynb` (File > Upload notebook).
3. Run all cells in order with Shift + Enter.

If the data link does not load, download the dataset from Kaggle, upload the CSV to Colab, and change the `pd.read_csv(...)` line to your file name.

## Future Improvements

- Try XGBoost and tune hyperparameters
- Add more features, such as the number of services used
- Use cross-validation for more stable results
- Build a small app (Streamlit) where a user can enter customer details and see the churn risk
- Add a Power BI dashboard of risk groups

## Author

**Subhashree Subhasmita**
B.Tech Computer Science, ITER, SOA
[LinkedIn](https://www.linkedin.com/in/subhashree-subhasmita-97a45a331) | [GitHub](https://github.com/Subhashree012005)
