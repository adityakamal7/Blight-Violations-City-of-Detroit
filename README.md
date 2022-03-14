# Blight-Violations-City-of-Detroit
To predict whether a given blight ticket will be paid on time

Blight violations are issued by the city to individuals who allow their properties to remain in a deteriorated condition. Every year, the city of Detroit issues millions of dollars in fines to residents and every year, many of these fines remain unpaid.

Each row corresponds to a single blight ticket, and includes information about when, why, and to whom each ticket was issued. The target variable is compliance, which is True if the ticket was paid early, on time, or within one month of the hearing data, False if the ticket was paid after the hearing date or not at all, and Null if the violator was found not responsible.

# Model Comparision and Summary
**1. XGBoost:**

        i.   Without over-sampled data set----- AUC: 0.82 || Precision: 0.90 || Recall: 0.26
        ii.  With over-sampled data set ------- AUC: 0.77 || Precision: 0.38 || Recall: 0.49
        iii. Using only important features ---- AUC: 0.82 || Precision: 0.90 || Recall: 0.26

**2. Random Forest:**

        i.   Without over-sampled data set----- AUC: 0.76 || Precision: 0.61 || Recall: 0.29
        ii.  With over-sampled data set ------- AUC: 0.73 || Precision: 0.34 || Recall: 0.44

**3. Logistic Regression:**

        i.   Without over-sampled data set----- AUC: 0.80 || Precision: 0.91 || Recall: 0.11
        ii.  With scaled data set ------------- AUC: 0.80 || Precision: 0.84 || Recall: 0.13
        iii. With over-sampled data set ------- AUC: 0.80 || Precision: 0.28 || Recall: 0.60

**4. Tuned XGBoost:**

        i.   Without over-sampled data set----- AUC: 0.82 || Precision: 0.90 || Recall: 0.26
        ii.  Using only important features ---- AUC: 0.82 || Precision: 0.90 || Recall: 0.26

In our case, with over-sampling of minority class, recall score increases while precision score decreases.

As enforcing unpaid blight fines is a costly and tedious process, we want our resources to be utilised effectively,i.e., allocating resources to follow up only those residents which are presicely going to be defaulter(not-paying). Hence, AUC and precision are used as evaluation metrics.

GridSearch tuned XGBoost model with only important features is selected because its AUC is 0.82 and precision score is 0.90 which is higher than other models and preferring only important features for modelling because of decrease in computational time.
