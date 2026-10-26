# Frito-Lay Employee Attrition Analysis (CaseStudy1DDS)
**Jorge Vazquez | DDSAnalytics | MSDS 6306 Doing Data Science**

Presentation Video: https://youtu.be/jknsxNU_t68?is=AA7rLj9RufEDJLSU

## Executive Summary

The goal of this project was to identify the factors related to employee attrition and to build a model that predicts which employees are likely to leave. Replacing an employee costs 50% to 400% of their salary, while a retention incentive costs $200 per employee, so an accurate model lets Frito-Lay target incentives where they matter. 

The given data has 870 employees, 140 of which left. Because the amount who left and those who stayed is imbalanced we will have to address that in the prediction model.

### Factors Related to Attrition
Every candidate feature was tested either with a welch two sample t test or a chi square test for numerical and categorical respectively.

The top 3 factors:

1. Overtime: 31.7% of overtime workers left compared with 9.7% of other employees.
2. No Stock Options: 25.9% of emplyees with no stock options left, compared with 3.7% to 7.6% at stock option level 1 and 2.
3. Low monthly income: 28.1% of employees earning under $3,000 a month left, compared with 9.3% of thse earning over $10,000.

Model Performance:
Two models built using all 18 significant features: KNN and Naive Bayes. At the default cut off, k =5 only caught 17.6% of leavers. Because only 16% of employees leave, most neighbors vote to stay at the company. To address the imbalance the probability cut off for predicting a person leaving was lowered. I selected the setting by averaging results over different random 70/20 splits.

From these tests, the tuned Naive Bayes is the best model. On the original split it caught 25 out of 34 employees who left.

Cost Impact: 
On the 261 employee test set, the tuned Naive Bayes Model flagged 79 employees, which costs $15,800 in incentives. It catches 25 of the 34 leavers. If the incentives does retain them, it saves the company anywhere from $466,600 to $3.8 million depending on the replacement costs.

Conclusion:

Use the model to target the $200 retention incentive
Review overtime levels for employees. 
Extend stock options to entry-level employees. 
Monitor sales representatives closely
