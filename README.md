# Transaction_Fraud_Detection
The goal of the project is to detect fraudulent behavior from the credit card transaction data of a government organization in 2010. The dataset contains 96,753 records with 10 fields and provides transaction details such as card number, date, merchant description, merchant zip, amount, and fraud label associated with each transaction.

## Summary
- I start with exploring the data and then clean it by identifying exclusion, removing outliers, and filling in missing values (1.Data_Exploration_Cleaning.ipynb)
- Then, I create 302 candidate variables from the original dataset, using combinations of variables related to card number, merchant, amount, date, and location. I also use Benford’s Law to detect unusualness in the card number and merchant number. Next, I apply a filter and wrapper method to identify the most important variables that can effectively capture fraudulent behaviors. This allows us to narrow down to the 28 most important variables (2.Feature_Engineering_Selection.ipynb)
- Finally, I build 3 supervised machine learning algorithms on our training data, including logistic regression, random forest, and boosted trees. For each algorithm, I try several models with different combinations of hyperparameters. For every combination of hyperparameters, I re-run the model 10 times and average the performance to get more robustness (3.Modeling.ipynb)

## Results
- I use the fraud detection rate (FDR) at 3% to measure the performance of each model. This tells us the percentage of fraud records caught in the top 3% of the dataset when it is sorted by the probability score of the model.
- For the final model with random forest, I achieve FDR at 3% of 0.57 on the test data.
- I find a score cutoff at 8% which maximizes the overall fraud savings under the following assumptions:
  - Saving per correct fraud caught: $2000
  - Opportunity/transaction loss from a record identified as a false positive: $50
