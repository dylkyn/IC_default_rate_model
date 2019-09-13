### PrePayment Model Project

### Goal
* The goal of this project was to predict default rates for a pool of loans, based on 4 attributes for each loan. 
* The features we used were:
    * Credit Score
    * LTV
    * DTI
    * Interest Rate

* Our label, or the value we were trying to predict, was default (a true or false variable)
* Ideally, given the data on a loan pool, one could run this model over every loan in the pool. The model, for every loan, would predict if it would be defaulted on. Then you could aggregate these scores for every loan in the pool to get the overall default rate.

### Data
* Data set consisted of 25 million+ loans from Freddie Mac Single Family Loan-Level Dataset
* The performance data set describes the performance of the loan over time (quarterly) until it was defaulted on or payed fully. 
* The acquistion data set describes information on the loan at the time it was lended out, and included attributes like credit score and Interest Rate.
* Due to their size, datasets were **not** included in this repo

### File Explanation
* ```Prepayment Model_AcqData.ipynb``` : file for exploring and gathering info on how the Acquisition Data is organized
* ```Clean_Data.ipynb```: grabs the foreclosure / default status from the performance data sets
* ```Join_Files.ipynb```: grabs the requested attributes from the Acquisition data set
* ```Model.ipynb```: trains, runs and tests the model. We chose to use logistic regression.

### Results
* Out of all the quarters for almost 20 years of data, with over 25 million loans, we only could run the model on about 8 quarters of data. This was because the data set was too large to run on our computing resources, and would take hours to run even on just 2 years of data.
* Because of this, our model accuracy (and more importantly, false negative and false positive rates) were not very high
* To improve accuracy in the future, we would run the data cleaning files and the model on more powerful resources
* Additionally, we would experiment with techniques besides logisitc regression and try to use different combinations of features.
* The results on our reduced data set are below:

```
Accuracy of the model: 0.7081416579062509
False Negatives: 0.2657210401891253
False Positive: 0.2918874671149677

```