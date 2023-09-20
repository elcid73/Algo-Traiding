# Algo-Traiding

Step 1: Tune the training algorithm by adjusting the size of the training dataset.

Results from reducing training window from 3 to 2 months:

                 precision    recall  f1-score   support

        -1.0       0.39      0.04      0.06      1825
         1.0       0.56      0.96      0.70      2318

    accuracy                           0.55      4143
   macro avg       0.47      0.50      0.38      4143
weighted avg       0.48      0.55      0.42      4143

Results from increasing training window from 3 to 6 months:

                 precision    recall  f1-score   support

        -1.0       0.44      0.02      0.04      1732
         1.0       0.56      0.98      0.71      2211

    accuracy                           0.56      3943
   macro avg       0.50      0.50      0.38      3943
weighted avg       0.51      0.56      0.42      3943

Increasing training window from 3 to 6 months resulted in increased Precision of sell signal from 0.39 to 0.44.  Recall for buy signal increased from 0.96 to 0.98 and dropped for sell signal from 0.04 to 0.02.

Step 2: Tune the trading algorithm by adjusting the SMA input features.

Results from reducing both SMA inputs (short_window = 2, long_window = 50):

                  precision    recall  f1-score   support

        -1.0       0.48      0.01      0.02      1757
         1.0       0.56      0.99      0.72      2244

    accuracy                           0.56      4001
   macro avg       0.52      0.50      0.37      4001
weighted avg       0.53      0.56      0.41      4001


Results from increasing both SMA inputs (short_window = 5, long_window = 180):

                 precision    recall  f1-score   support

        -1.0       0.45      0.06      0.10      1669
         1.0       0.56      0.95      0.71      2140

    accuracy                           0.56      3809
   macro avg       0.51      0.50      0.40      3809
weighted avg       0.52      0.56      0.44      3809

Reducing both SMA inputs appears to give marginally better results than increasing them.


Step 3: Choose the set of parameters that best improved the trading algorithm returns.

I chose the original SMA inputs and 6 months traiding:

                precision    recall  f1-score   support

        -1.0       0.44      0.02      0.04      1732
         1.0       0.56      0.98      0.71      2211

    accuracy                           0.56      3943
   macro avg       0.50      0.50      0.38      3943
weighted avg       0.51      0.56      0.42      3943

This model does better predicting buy signals after early 2020, but does worse than the original model in the period of 2019 - early 2020



Evaluate a New Machine Learning Classifier.

I used Logistic Regression for updated trading algorith, which performed much worse than fine tune original trading model (predicting buy signals was very weak):

                precision    recall  f1-score   support

        -1.0       0.44      0.84      0.57      1425
         1.0       0.56      0.16      0.25      1838

    accuracy                           0.46      3263
   macro avg       0.50      0.50      0.41      3263
weighted avg       0.51      0.46      0.39      3263















