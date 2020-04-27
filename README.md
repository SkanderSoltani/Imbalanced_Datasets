# Handling Imbalaced Datasets - Deep Learning

## Introduction
An imbalaced dataset is a dataset in which the class of interest (1), the minority class, is much rarer than the rest of the clases (0). 

![](images/sample_data.PNG)

Learning from imbalanced datasets like the one represented by the chart above is challenging and often leads to disappointing results if conventional ML techniques are applied. This happens because classifiers are based on optimization methods designed to improve overall accuracy and reduce error without considering the proportion / balance of classes. Such approach will often result in misclassifying the class of interest (The minority class) and lead to poor out of sample results; especially if the cost of missing the minority class is much higher than the cost of missing the majority class. This issue is predominant in problems where anomaly detection is decisive like fraudulent transaction in banks or identifying rare diseases. In this research project we will apply a Neural Network classifier along with a few tricks on a highly unbalanced dataset representing Credit Card transactions with a goal of correctly classify out of sample fraudulent transactions.     

## Acknowledgements
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. More details on current and past projects on related topics are available on https://www.researchgate.net/project/Fraud-detection-5 and the page of the DefeatFraud project.

## Dataset Description 

Source: https://www.kaggle.com/mlg-ulb/creditcardfraud
The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, ... V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

## Challenges: 

### Imbalanced data challenge:
The challenges faced with the credit card transactions data set is that fraudulent transactions represent only 0.172% of the total number of transactions. The ask is to find a classifier model that improves the identification of the minority class as opposed to achieving higher overall accuracy.  

### The challenges of using conventional ML techniques:
1)  The standard performance measures such as accuracy or even the Area Under the Curve (AUC) do not provide an accurate performance measure when faced with imbalanced data sets. You can find more information on different performance measures here:https://en.wikipedia.org/wiki/Precision_and_recall 

2) Conventional regression based classifiers such as Neural Network, Logistic Regression, etc. with a traditional Logit cost function of the form: $Cost = -\frac{1}{m} \sum_{i=1}^{m}(y^ilog(h_{\theta(x^i)}+(1-y^i)log(1-h_{\theta}(x^i)) + \lambda * L_{PenaltyTerm}$   are biased towards the majority class that has the larger number of instances. These algorithms tend to predict accurately only focus on the majority class data, while all the features of the minority classes are often treated as noise. Hence, there is high probability of misclassifying the minority class (Predicting that a transaction is not fraudulent when in fact it is) which can result to hefty cost to the bank or credit card company. For more information on the dynamics underlying the logistic cost function LOGIT, you can watch the following video by Professor Andrew Ng:https://www.youtube.com/watch?v=SHEPb1JHw5o 

<img src="https://render.githubusercontent.com/render/math?math=Cost = -\frac{1}{m} \sum_{i=1}^{m}(y^ilog(h_{\theta(x^i)}+(1-y^i)log(1-h_{\theta}(x^i)) \plus\lambda * L_{PenaltyTerm}">
```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/SkanderSoltani/Imbalanced_Datasets/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
