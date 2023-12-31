# Income Classification Model:

## Business Problem and Stakeholders

The aim of this project is to predict an individual's annual income category based on various factors. The stakeholders for this analysis could include financial institutions, marketing agencies, and governmental organizations looking to understand income distributions and make data-driven decisions related to financial services, marketing strategies, and policy-making.

## Source of Data

The dataset used for this analysis was sourced from Kaggle:
[Adult Income Dataset](https://www.kaggle.com/datasets/wenruliu/adult-income-dataset)

## Description of Data

The dataset comprises information on 48,842 individuals and contains 15 features that could potentially influence an individual's income. Some of the key features include education level, age, gender, occupation, etc. For a detailed description of the dataset, refer to the [original UCI documentation](http://www.cs.toronto.edu/~delve/data/adult/adultDetail.html).

## Analytical Insights

The analysis yielded the following key insights:

1. **Hours per week vs. Income**: A clear correlation exists between an individual's hours of work per week and their income category, with a highest income for those how work  between 30 and 40 hours a week.

2. **Age and Income Distribution**: Certain age categories show a significant skew in income distribution, with some age groups having a highest representation in high income categorie.

## Model Evaluation:

# Before PCA:

1. **Logistic Regression:**
High precision, recall, and accuracy for the '<=50K' class.
Reasonable precision for '>50K' but low recall.
Overall good performance, especially for the majority class.

2. **KNN:**
Moderate precision and recall for both classes.
Balanced performance for both classes, considering the class imbalance.

3. **Random Forest:**
Similar to Logistic Regression, with slightly better performance for the '>50K' class.

# After PCA:

1. **Logistic Regression:**
Significant drop in performance for the '>50K' class after PCA, affecting recall and F1-score notably.

2. **KNN:**
After PCA, significant decrease in performance for the '>50K' class, especially in recall and F1-score.

3. **Random Forest:**
Maintains relatively consistent performance after PCA, with slight decreases in the '>50K' class metrics.

## Choosing the Model:
Considering the business problem and class balance, Random Forest might be more suitable:

Logistic Regression: Initially performed well for both classes but had a substantial decrease in '>50K' class performance after PCA.

Random Forest: Showed consistent performance for both classes, even after PCA.

# Stakeholder Impact:

**False Positives:** Predicting '>50K' when it's actually '<=50K' might lead to misallocation of resources (e.g., targeting low-income groups for premium services).

**False Negatives:** Predicting '<=50K' when it's actually '>50K' might miss opportunities (e.g., not offering suitable financial products to eligible customers).

# Model Description:
The chosen model (Random Forest) performs well, especially in predicting the majority class ('<=50K'). However, it struggles with the minority class ('>50K'), leading to decreased recall and F1-score. This imbalance might affect stakeholders:

False positives might misallocate resources.
False negatives might miss opportunities for valuable customers.
Ensuring that stakeholders understand the model's limitations regarding false predictions can help them make more informed decisions and mitigate potential risks associated with misclassifications, especially in handling the minority class. Regular model monitoring and updates might further enhance its performance in predicting both income categories accurately.
