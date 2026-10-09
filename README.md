# Bank Marketing Data Mining & Classification

## Project Overview

This project applies data mining and machine learning techniques to a bank marketing dataset to investigate customer subscription behaviour and predict whether a customer is likely to subscribe to a term deposit.

The project combines exploratory data analysis, statistical testing, classification modelling, MLflow experiment tracking, and an interactive Power BI dashboard to support data-driven marketing decisions.

## Business Problem

Bank marketing campaigns require time and resources to reach potential customers. Identifying customers who are more likely to subscribe can help marketing teams prioritise outreach, improve campaign targeting, and evaluate campaign effectiveness.

The objective is to build a classification model that predicts customer subscription outcomes using available demographic, financial, and campaign-related attributes.

## Objectives

- Explore customer and campaign data to identify patterns and relationships.
- Assess data quality, distributions, class imbalance, and potential outliers.
- Investigate factors associated with term-deposit subscription.
- Train and compare classification models.
- Evaluate model performance, particularly its ability to identify actual subscribers.
- Track model experiments using MLflow.
- Present predictions and performance metrics in Power BI.

## Tools and Technologies

- **Python:** Data analysis and model development
- **Pandas and NumPy:** Data preparation and manipulation
- **Scikit-learn:** Preprocessing, model training, cross-validation, tuning, and evaluation
- **MLflow:** Experiment tracking and model logging
- **Google Colab:** Development environment
- **Power BI:** Interactive reporting and visualisation
- **Git and GitHub:** Version control and project documentation

## Project Workflow

1. **Data preparation:** Inspected the dataset, checked for missing values and duplicates, and prepared the target variable.
2. **Exploratory data analysis:** Examined subscription distribution, numerical variables, categorical variables, and outliers.
3. **Statistical analysis:** Used association measures and statistical tests to investigate relationships between customer attributes and subscription outcomes.
4. **Feature preparation:** Encoded categorical variables and excluded the `duration` variable to avoid relying on information only available after a call.
5. **Model development:** Trained a Decision Tree and Random Forest classifier.
6. **Model tuning:** Used cross-validation and grid search to identify a suitable Random Forest configuration.
7. **Model evaluation:** Evaluated predictions on a held-out test set using precision, recall, F1-score, accuracy, and a confusion matrix.
8. **Experiment tracking:** Logged model parameters and evaluation metrics with MLflow.
9. **Business reporting:** Exported test-set predictions and performance metrics for visualisation in Power BI.

## Model Performance

The tuned Random Forest was evaluated on a stratified 20% holdout test set containing 9,043 records.

| Metric | Result |
|---|---:|
| Accuracy | 86.7% |
| Subscriber precision | 44.5% |
| Subscriber recall | 53.5% |
| Subscriber F1-score | 48.5% |

### Confusion Matrix

| | Predicted: No | Predicted: Yes |
|---|---:|---:|
| Actual: No | 7,278 | 707 |
| Actual: Yes | 492 | 566 |

The model correctly identified 566 actual subscribers and missed 492. Of the customers predicted to subscribe, approximately 44.5% actually subscribed in the test set.

Although overall accuracy was relatively high, subscriber precision and recall indicate that further improvements could be useful. The model should therefore support campaign prioritisation rather than be treated as a guarantee of customer behaviour.

## Power BI Dashboard

The Power BI report presents the model results in a business-friendly format, including:

- Total customers evaluated
- Actual and predicted subscribers
- Model accuracy
- Comparison of actual and predicted subscription outcomes
- Predicted subscriber breakdown by job category
- Customer-level predictions and subscription probabilities

**Scope:** The dashboard's prediction results represent the held-out test set, not live predictions for the bank's entire customer base.

## Key Findings

- The target variable was imbalanced, with approximately 11.7% of records representing subscribers.
- Previous campaign outcome had the strongest categorical association with subscription among the variables assessed.
- Subscription rates varied across contact months and job categories.
- The age comparison was not statistically significant at the 5% level in the test performed.
- Model performance should be assessed using precision, recall, and F1-score alongside accuracy because subscriber and non-subscriber outcomes are imbalanced.

These findings describe patterns in the dataset and statistical associations; they do not establish causation.


## How to Run

1. Clone this repository.
2. Install the required Python packages listed in `requirements.txt`.
3. Obtain the dataset and follow the loading instructions in `data/README.md`.
4. Open the notebook in Jupyter or Google Colab.
5. Run the analysis and modelling workflow.
6. Open the `.pbix` file in Power BI Desktop to explore the report.

## Limitations and Future Improvements

- Improve identification of subscribers while balancing false positives and false negatives.
- Evaluate alternative classification algorithms and probability thresholds.
- Validate performance on additional or more recent campaign data.
- Investigate model calibration and the business cost of incorrect predictions.
- Extend the reporting layer with statistical findings and deeper customer-segment analysis.

## Data Source

The project uses the Bank Marketing dataset from the UCI Machine Learning Repository.

https://archive.ics.uci.edu/dataset/222/bank+marketing

Please review the dataset's licence and terms before redistributing the data.

## Disclaimer

This project is for educational and portfolio purposes. The model's predictions are estimates based on historical data and should not be interpreted as certain customer outcomes.
