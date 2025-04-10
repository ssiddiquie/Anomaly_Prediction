# Anomaly Prediction in Sensor Data

This project focuses on developing a binary classification model to detect rare events (anomalies) in sensor data. Given the highly imbalanced nature of the dataset, the workflow encompasses data preprocessing, feature engineering, model training, evaluation, and prediction generation.

## Project Overview

Anomalies in sensor data can indicate critical issues requiring prompt attention. This project aims to build robust models capable of accurately identifying such anomalies. The workflow includes:

1. **Data Loading**: Importing the training and test datasets.
2. **Feature Engineering**: Creating time-based features from timestamps.
3. **Outlier Handling**: Applying Winsorization to manage outliers in sensor readings.
4. **Data Preprocessing**: Scaling sensor data and addressing class imbalance.
5. **Model Training**: Training multiple classifiers, including RandomForestClassifier, XGBClassifier, and LGBMClassifier.
6. **Model Evaluation**: Assessing model performance using metrics such as accuracy, F1 score, and classification reports.
7. **Threshold Tuning**: Adjusting decision thresholds to optimize the F1 score.
8. **Prediction Generation**: Producing predictions on the test dataset for submission.

## Dataset

The dataset comprises sensor readings with the following structure:

- **Features**: 'Date', 'X1', 'X2', 'X3', 'X4', 'X5'
- **Target**: Binary indicator of anomaly (0 for normal, 1 for anomaly)

The training set contains 1,639,424 instances, while the test set includes 409,856 instances.

## Usage

1. **Data Loading**: Load the training and test datasets.
2. **Feature Engineering**: Generate time-based features from the 'Date' column.
3. **Outlier Handling**: Apply Winsorization to the sensor columns to mitigate the impact of outliers.
4. **Data Preprocessing**:
   - Scale sensor data using StandardScaler.
   - Address class imbalance by converting the target variable to integer type.
5. **Model Training**: Train the following classifiers:
   - RandomForestClassifier
   - XGBClassifier
   - LGBMClassifier
6. **Model Evaluation**: Evaluate each model's performance on the validation set using accuracy, F1 score, and classification reports. Visualize feature importances and correlation heatmaps.
7. **Threshold Tuning**: Adjust the decision thresholds for each model to optimize the F1 score. This involves:
   - Generating prediction probabilities.
   - Evaluating performance across a range of thresholds.
   - Selecting the threshold that yields the highest F1 score.
8. **Prediction Generation**: Use the best-performing model to predict anomalies in the test set and save the results for submission.

## Results

Through threshold tuning, the optimal thresholds and corresponding F1 scores achieved are:

- **RandomForestClassifier**: Threshold = 0.8437, F1 Score = 0.6082
- **XGBClassifier**: Threshold = 0.9634, F1 Score = 0.5742
- **LGBMClassifier**: Threshold = 0.9671, F1 Score = 0.5476

## Contributing

Contributions to enhance the model's performance or extend its capabilities are welcome. Please fork the repository and submit a pull request with your improvements.

## License

This project is licensed under the MIT License.

## Acknowledgments

Special thanks to the contributors and the community for their support and resources that facilitated this project. 
