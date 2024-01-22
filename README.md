This project focuses on predicting the active power output of wind turbines using time series data. Here's an overview of the project:

1. *Data Processing*:
   - The dataset is loaded and the timestamp information is extracted and set as the index.
   - Duplicate entries are removed, resulting in a dataset with 95,185 records and 19 features.
   - Several features with low variability are dropped, reducing the dataset to 19 columns.

2. *Data Exploration and Visualization*:
   - Unique value counts for each column are examined, revealing significant diversity in 'ActivePower' and 'WindSpeed'.
   - Visualizations are created to understand the relationship between 'WindSpeed' and 'ActivePower'.
   - Data is resampled to daily and monthly intervals for further analysis.

3. *Feature Selection*:
   - Correlation analysis and a heatmap are utilized to quantify the relationships between features.
   - 'WindSpeed' is identified as the primary feature with the highest correlation to 'ActivePower'.

4. *Model Training and Testing*:
   - The dataset is manually split into training (78,000 samples) and testing (989 samples) sets, as traditional train-test splitting methods are unsuitable for sequential time series data.
   - An XGBoost regressor model with 200 estimators is created and trained. Early stopping is implemented to prevent overfitting.

5. *Model Evaluation*:
   - The model's performance is assessed using various metrics, including R-squared, Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and Mean Absolute Percentage Error (MAPE).
   - The model demonstrates a high R-squared value of 0.970, indicating strong predictive capability.

6. *Predicting Future Values*:
   - A scenario is explored where 'WindSpeed' data is unavailable, and features are generated using datetime information.
   - A separate model is trained, achieving less accurate predictions compared to the 'WindSpeed'-based model.

7. *Saving the Model*:
   - The trained model is saved in both XGBoost's native format and as a pickle file for future use, demonstrating compatibility with Flask applications.

This project showcases a comprehensive approach to time series prediction, encompassing data preprocessing, visualization, feature selection, model training, and evaluation. 
The use of XGBoost, a powerful ensemble learning algorithm, along with careful feature engineering and model evaluation techniques, contributes to accurate predictions of wind turbine active power.
