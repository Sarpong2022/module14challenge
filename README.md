# Algorithmic Trading Bot

A Jupyter notebook that contains an algorithmic trading bot that learns and adapts to new data and evolving markets.

The data set can be found in the [`Resources`](Resources/) folder:

- [emerging_markets_ohlcv.csv](Resources/emerging_markets_ohlcv.csv)

---

## Technologies

- python 3.9.13
- jupyterlab 3.4.4
- pandas 1.4.4
- numpy 1.12.3
- hvplot 0.8.8
- scikit-learn 1.1.1

---

## Evaluation Report

### Baseline performance

The baseline model used 3 momths of training data and had a fast window of 4 and a long window of 100. This model showed positive results when used to predit the test data, and the strategy was mostly in the green throughout the test period.

<img src="images/baseline.png" width="450" height="300">

### What impact resulted from increasing or decreasing the training window?

Decreasing the training window to 2 months showed similar, but less positive results as compared to 3 months.

<img src="images/2mo.png" width="450" height="300">

Increasing the training window to 6 months showed more positive results overall, but resulted in a period just over a year where the strategy was in the red.


<img src="images/6mo.png" width="450" height="300">

### What impact resulted from increasing or decreasing either or both of the SMA windows?

Increasing or decreasing the SMA windows did not seem to make a big differences to the overall strategy returns as demonstrated in the following 4 images. None of the attempted changes resulted in a better model.

<img src="images/3mo_2_100.png" width="450" height="300">
<img src="images/3mo_8_100.png" width="450" height="300">
<img src="images/3mo_4_50.png" width="450" height="300">
<img src="images/3mo_4_150.png" width="450" height="300">

However, increasing the training window to 6 months and increasing the fast SMA window to 8 seemed to give the best results with the highest overall Strategy Returns.

<img src="images/3mo_8_100.png" width="450" height="300">

### Evaluate A New Machine Learning Classifier

In evaluating different machine learning classifiers, the AdaBoostClassifier model performed the best with a slighlty higher cumulative return than the SVM Classifier model. The LogisticRegression and DecisionTreeClassifier models both resulted in a cumulative loss by the end of the testing period, however, they also had periods where they saw cuulkative gains. While the AdaBoostClassifier model performed the best with the original parameters (compared to baseline), the tuned model with the 6 month training window and 8 period fast SMA still perfomed better overall.

<img src="images/ml_compare.png" width="450" height="300">

---

