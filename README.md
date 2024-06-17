# DibyaRanjanSamal_Datahack
In this project, I tackled a multilabel classification problem to predict vaccination probabilities using a comprehensive data processing and machine learning approach. Below are the detailed steps of my methodology:

1. Data Preparation and Merging
First, I combined the training feature set and the corresponding labels to form a unified dataset. This step ensured that each row in the dataset contained both the features and the target labels, making it easier to manage and process the data comprehensively.

2. Handling Missing Values
To address missing values in the dataset, I employed a mode-based imputation method. This approach filled the null entries with the most frequent value for each respective column, maintaining the integrity and representativeness of the data.

3. Feature Selection
After handling the missing values, I conducted a feature selection process. I identified and removed several columns that were deemed unnecessary for the prediction task. The columns excluded included education, race, hhs_geo_region, census_msa, employment_industry, and employment_occupation. This step helped streamline the dataset and focus on the most relevant features.

4. Encoding Categorical Variables
Next, I transformed the categorical features into numerical values suitable for machine learning algorithms:

     Ordinal Encoding:  I applied ordinal encoding to the age and income columns. This technique is particularly effective for variables where the order or ranking of categories holds significance.
     One-Hot Encoding:  For categorical features such as employment, marital status, sex, and rent or own, I utilized one-hot encoding. This method converted these categorical variables into a series of binary 
                       columns, ensuring that each category was represented as a unique column.
5. Model Training
For the model training phase, I implemented a multilabel gradient boosting classifier. Gradient boosting is a powerful ensemble learning technique that builds a predictive model by combining multiple weak learners, typically decision trees, to create a robust classifier. This method is particularly effective for handling complex, multilabel classification tasks.

6. Model Evaluation
To evaluate the performance of the model, I used the ROC AUC (Receiver Operating Characteristic - Area Under the Curve) score. The ROC AUC score is a reliable metric for assessing the performance of classifiers, especially in binary and multilabel settings, as it considers the trade-off between the true positive rate and the false positive rate across different thresholds.

7. Applying the Model to Test Data
Following the same preprocessing approach used for the training data, I prepared the test data features for prediction. This involved encoding categorical variables and ensuring the test data matched the format used during the training phase.

Using the trained multilabel gradient boosting classifier, I predicted the probabilities for the target labels on the test dataset. These predictions provided insights into the likelihood of each label being true for the given test instances.

8. Creating the Final Output
Finally, I constructed a new DataFrame by merging the predicted probabilities with the respondent_id from the test dataset. This step ensured that each prediction was clearly associated with the corresponding respondent. I then saved this combined DataFrame as a CSV file, which encapsulated the prediction results in a structured and easily accessible format.
