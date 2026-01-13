# Prediction Problem and Description:
The problem at hand is a classification problem of predicting whether a credit card client will default or not. For this problem, we will use [Default of Credit Card Clients Dataset](https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset). In this data set, there are 30,000 examples and 24 features, and the goal is to estimate whether a person will default (fail to pay) their credit card bills; this column is labeled "default.payment.next.month" in the data.

Our mini project will focus on the dataset described above. [Default of Credit Card Clients Dataset](https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset) contains personal information about  30 000 bank clients (`SEX`, `EDUCATION`, `MARRIAGE`) as well as their transaction and repayment history from April 2005 to September 2005 (`PAY_0`, `BILL_AMT1`, `PAY_AMT1`). As described in the prediction problem, we will use binary classification to predict whether a credit card client will default or not(`default.payment.next.month`). A value of 1 indicates the client defaulted, while 0 indicates they paid on time. From a practical perspective, such a model would help banks and financial institutions reduce their risk of incurring 'bad debt' by avoiding clients likely to 'default'. Additionally, by identifying which features of a client's financial history and personal characteristics most strongly influence the likelihood of default, banks could proactively offer solutions, such as financial education programs. These programs would help clients manage their finances more effectively. In turn, this supports a healthier flow of capital that drives economic growth.

At first glance, we noticed that:  
  - Every feature is represented numerically, even the categorical features such as `MARRIAGE` and `EDUCATION`
    - All categorical variables (`MARRIAGE`, `SEX`, `EDUCATION`) don't have a natural order between the numeric values, and therefore, OneHotEncoding is likely required
  - There are no missing values within any feature column as described by: https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients, as well as seen in the `train_df.describe()` table below.
  - Repayment History (`PAY_0` to `PAY_6`) is likely crucial, as it captures a client's past ability to make payments for the credit card statement, which is probably indicative of their future habits
  - Bill Amounts and Payment Amounts (`BILL_AMT1`, `PAY_AMT1`) are likely correlated, as alongside other features, could provide insights into the financial behaviour of a client's ability to manage their debt
  - ID is unique for each customer and therefore an identifier rather than a useful feature for our predictive model
  - Education has two values that map to 'unknown' which we will want to combine to reduce redundancy.
  - The Datset does illustrate how to interpret values 0, and -2 present within the `PAY` columns, and thus no assumptions will be made, and the data will be treated independetly of the -1 and 1-9 which have a natural order. There is a response from the author in this discussion on what they mean: https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset/discussion/34608, which we will be utilizing to interpret the values.
  - It is important to note that the dataset is from bank customers in Taiwan, with monetary values being in New Taiwan dollars

Overall, this dataset provides 22 features that likely correlate with predicting whether a customer will default, offering a practical application of what we have learned about classification towards risk prediction and financial decision-making.

# Technologies Used:
- Python
- Scikit-learn
- NumPy
- Pandas
- Matplotlib
- Seaborn
