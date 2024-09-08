Predicting Hazardous Near-Earth Objects (NEOs)
Project Overview:
This project aims to predict whether a Near-Earth Object (NEO) is hazardous or not using machine learning techniques. The dataset used tracks NEOs observed by NASA between 1910 and 2024. 
Predicting hazardous NEOs is crucial for planetary defense and preventing possible collisions with Earth.

Dataset:
The dataset contains 338,199 records, each representing an object in space. Key features include:
Diameter: Size of the object in kilometers.
Velocity: Speed of the object in km/h.
Magnitude: Visual brightness of the object.
Distance from Earth: Distance from the Earth in AU.
is_hazardous: Target variable, indicating whether the object is hazardous (1) or not (0).
The dataset can be downloaded from Kaggle: NASA Nearest Earth Objects Dataset.

Project Details:
1. Data Importing:
The dataset is imported using pandas, a powerful data manipulation library in Python. We load the data into a pandas DataFrame to facilitate easy access and manipulation.

2. Data Cleaning:
Data cleaning involves handling missing values, irrelevant columns, and ensuring all the data is in the correct format for modeling. The raw dataset may contain missing or irrelevant values that can affect the performance of the machine learning model.
Steps in Data Cleaning:
Handling Missing Values: Missing values can significantly impact model performance. In this project, any rows with missing values are removed to ensure data integrity with (dropna()).
Dropping Irrelevant Columns: The dataset contains columns that are not useful for the model. For example, object names such as (2013 RB21) do not provide any numerical or categorical insights that the model can use. These columns are dropped to streamline the data.

3. Exploratory Data Analysis (EDA):
Correlation Matrix: We examined the correlation between features to understand their relationships.
Distribution of Hazardous NEOs: Plots were used to visualize the distribution of hazardous and non-hazardous NEOs.

4. Data Preprocessing:
Handling Missing Values: The dataset was cleaned by dropping rows with missing values.
Feature Selection: Only relevant features like estimated_diameter_max, relative_velocity, magnitude, and distance_from_earth were kept. Non-numeric columns like object names were removed.
Dealing with Class Imbalance: Since hazardous NEOs are far fewer than non-hazardous ones, we used SMOTE (Synthetic Minority Over-sampling Technique) to balance the classes.
Data Scaling: Standardized the numeric features using StandardScaler to ensure uniformity in model training.

5. Model Training and Evaluation:
Model Used: We trained a Random Forest Classifier to predict whether a NEO is hazardous.
Handling Imbalance: SMOTE was applied to balance the class distribution before training the model.
Metrics Used: The model was evaluated using multiple metrics such as:
Precision: Indicates how many of the predicted hazardous NEOs were actually hazardous.
Recall: The percentage of actual hazardous NEOs that were correctly identified.
F1-Score: A harmonic mean of Precision and Recall.
ROC AUC Score: A robust metric for imbalanced datasets.

Results:
Precision: The ability of the model to correctly identify hazardous NEOs.
Recall: The ability to capture all hazardous NEOs.
ROC AUC Score: Indicates how well the model distinguishes between hazardous and non-hazardous objects.
Confusion Matrix: Visualizes the number of correct and incorrect predictions.

Conclusion:
The Random Forest Classifier performed well in predicting hazardous NEOs. By handling class imbalance with SMOTE and scaling the data appropriately, we were able to achieve meaningful predictions. Further optimization, such as hyperparameter tuning or using other models like XGBoost, could improve performance.

