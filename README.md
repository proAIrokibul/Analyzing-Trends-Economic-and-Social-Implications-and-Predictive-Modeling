# Analyzing Trends, Economic and Social Implications, and Predictive Modeling of Coastal Waste Risk

## Objective
The objective of this project is to analyze the trends, economic and social implications, and perform predictive modeling on plastic waste data. The key aim is to predict the level of **Coastal Waste Risk** using various machine learning models. The dataset includes crucial factors such as **total plastic waste**, **main sources of waste**, **recycling rate**, **per capita waste**, and **coastal waste risk**, which have been evaluated to understand the relationship between waste generation and the impact on coastal areas.

## Dataset Overview
The dataset contains the following columns:
- **Country**: The country where the data was collected.
- **Total_Plastic_Waste_MT**: The total plastic waste generated in metric tons.
- **Main_Sources**: The primary sources of plastic waste.
- **Recycling_Rate**: The recycling rate as a percentage.
- **Per_Capita_Waste_KG**: The amount of plastic waste per capita in kilograms.
- **Coastal_Waste_Risk**: The target variable indicating the risk level associated with coastal waste.

## Preprocessing
Data preprocessing involved several essential steps:
1. **Handling Missing Values**: All columns had complete data with no null values, ensuring no imputation was necessary.
2. **Encoding Categorical Variables**: Label Encoding was performed on the **Country** and **Main_Sources** columns to convert categorical values into numerical form for machine learning models.
3. **Data Normalization**: The numerical features were scaled to improve model convergence and performance.

## Modeling
Three different classification models were applied to predict the **Coastal_Waste_Risk**:

### 1. Logistic Regression:
- **Accuracy**: 54.55%
- **Precision (Class 0)**: 50%, **Recall (Class 0)**: 92%, indicating that for the low-risk coastal areas, the model correctly identified them with a high recall but struggled to identify all the instances correctly (low precision).
- **Precision (Class 1)**: 56%, **Recall (Class 1)**: 45%, highlighting the model's inability to correctly predict the moderate-risk class with a balanced performance.
- **Precision (Class 3)**: 0%, **Recall (Class 3)**: 0%, showing poor prediction performance for this class, which may be due to the limited representation of this class in the dataset.
- **Weighted Avg. Accuracy**: 55%

### 2. Random Forest Classifier:
- **Accuracy**: 54.55%
- **Precision (Class 0)**: 50%, **Recall (Class 0)**: 92%, similar to Logistic Regression, the model shows high recall for class 0 but lower precision.
- **Precision (Class 1)**: 57%, **Recall (Class 1)**: 36%, showing a similar trend where the model struggles with predicting the moderate-risk class accurately.
- **Precision (Class 3)**: 100%, **Recall (Class 3)**: 100%, indicating the model was able to perfectly predict the rare class (Class 3), likely due to overfitting on this rare class.
- **Macro Avg. F1-Score**: 61%

### 3. Gradient Boosting Classifier:
- **Accuracy**: 57.58%
- **Precision (Class 0)**: 50%, **Recall (Class 0)**: 83%, reflecting improved recall for the low-risk coastal areas compared to Logistic Regression and Random Forest.
- **Precision (Class 1)**: 56%, **Recall (Class 1)**: 45%, similar to other models, this class had moderate prediction performance.
- **Precision (Class 2)**: 100%, **Recall (Class 2)**: 33%, showing that while the model can predict some Class 2 cases with high precision, it fails to capture all instances.
- **Macro Avg. F1-Score**: 66%

## Results Comparison
1. **Accuracy**: The Gradient Boosting model performed the best with an accuracy of 57.58%, followed by Logistic Regression and Random Forest Classifier at 54.55%.
2. **Precision and Recall**:
   - **Class 0 (Low Risk)**: Logistic Regression and Random Forest performed similarly with high recall but lower precision.
   - **Class 1 (Moderate Risk)**: All models showed difficulty in predicting this class with balanced precision and recall.
   - **Class 3 (High Risk)**: All models performed well with a perfect recall and precision for this rare class, indicating that it might be overfitted due to the class imbalance.
3. **Model Performance**: The **Gradient Boosting** model offered the highest **Macro Average F1-score (66%)**, which suggests better overall performance in balancing precision and recall for all classes.

## Conclusion
The models showed varying degrees of success in predicting **Coastal_Waste_Risk**. While **Gradient Boosting** demonstrated the best accuracy and macro-average F1-score, there is significant room for improvement, particularly in predicting the **moderate risk** class. **Logistic Regression** and **Random Forest** exhibited similar performance but were less effective in capturing the complexities of the dataset.


