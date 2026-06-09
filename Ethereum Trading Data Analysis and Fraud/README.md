<img width="603" height="283" alt="Screenshot 2026-06-09 at 4 31 14 PM" src="https://github.com/user-attachments/assets/3df5dcd7-3ef8-40d1-9a3f-7dad204b6686" />

Purpose: Develop a classifier to predict fraudulent transactions.
Data Source: Kangle.
Steps:

         - Data preparation.

         - Feature extraction.

         - Model prediction.

         - Conclusion and Plan to improve prediction.

​Technical Skills: 

         - Analyze the variance of feature distributions.

         - Eliminate duplicate rows.

         - Fill the missing value rows by "Mean."
         - Analyze correlations between variables.
         - Split data and handle imbalanced problem by SMOTE method.

         - Implement Principle Component Analysis (PCA).

         - Implement K_fold_test function.

         - Develop Modeling Prediction.

         - Evaluate a given model using cross-validation.

         - Evaluate the models and store results.

         - Visualize model performance for comparison.
         
<img width="583" height="885" alt="Screenshot 2026-06-09 at 4 32 42 PM" src="https://github.com/user-attachments/assets/6b99750d-6ce4-4e03-8ff8-79b8df0b852c" />

<img width="847" height="809" alt="Screenshot 2026-06-09 at 4 33 21 PM" src="https://github.com/user-attachments/assets/2d1a80d1-d54a-41e0-bfd6-73a6af7c9145" />

                  Correlation Matrix Interpretation 

1. Significant Positive Correlations:
   - Unique Sent To Addresses and Unique Received From Addresses: Strong positive correlation of 1.
   - Max value received and avg val received: Correlation of 0.62.
   - Max val sent and avg val sent: Correlation of 0.6.
   - ERC20 uniq rec addr and ERC20 uniq sent addr: Correlation of 0.73.
   - ERC20 uniq rec addr and ERC20 uniq sent addr.1: Correlation of 0.57.
2. Significant Negative Correlations:
   - FLAG and Time Diff between first and last (Mins): Correlation of -0.22, indicating that as the FLAG value increases, the time difference between the first and last transactions tends to decrease.
3. Other Observations:
   - Features related to values (e.g., max value received, avg val received, max val sent, avg val sent) show moderate positive correlations among themselves.
   - ERC20-related features (e.g., ERC20 uniq rec addr, ERC20 uniq sent addr, ERC20 uniq sent addr.1) show positive correlations with each other, indicating some degree of relationship among these features.
4. Importance:
   - Feature Selection: Highly correlated features might provide redundant information. Depending on the use case, it might be beneficial to select only one of the highly correlated features to reduce multicollinearity in the model.
   - Model Insights: Understanding correlations helps in interpreting model predictions and ensuring the robustness of the model.
5. Next Steps:

    - Detect Multicollinearity by VIF.
    - Address Multicollinearity: Consider techniques such as Principal Component Analysis (PCA) or removing some of the highly correlated features.

 Principal Component Analysis (PCA)

Certainly, the maximum values and averages demonstrate a strong correlation. Similarly, the number of ERC20 token transactions sent to unique account addresses (ERC20UniqSent_Addr) and the number of ERC20 token transactions received from unique addresses (ERC20UniqRec_Addr) also show high correlation. However, there is no significant multicollinearity among the features.
I utilized Principal Component Analysis (PCA) to potentially enhance the performance of an XGBoost binary classifier, though its effectiveness varies based on the specifics of your dataset and problem. PCA can impact your XGBoost model in several ways: Dimensionality Reduction, Noise Reduction, Improved Training Speed, Feature Engineering.

<img width="632" height="950" alt="Screenshot 2026-06-09 at 4 34 49 PM" src="https://github.com/user-attachments/assets/5fe36ba8-5261-40a4-b137-9d3f74bf8f10" />

I used the SMOTE technique to address the imbalance issue when splitting the data into training and testing sets.

In this problem, I observe that in Ethereum trading, there are 1,656 fraudulent transactions and 7,632 non-fraudulent ones. This means the dataset is imbalanced, with only 17.829% of transactions being fraudulent. A simple binary classifier might achieve a high accuracy of 82.171% by predicting most transactions as non-fraudulent. However, in such skewed class distributions, accuracy is not a reliable metric.

Imbalanced datasets are a common challenge in binary classification problems, often seen in practical applications like fraud detection, spam filtering, rare disease identification, and hardware fault detection. One effective technique to address this issue is the Synthetic Minority Oversampling Technique (SMOTE). SMOTE generates synthetic samples for the minority class, helping to balance the dataset.

The significance of SMOTE lies in its ability to handle class imbalance, thereby improving the performance of classifier models. By reducing bias and capturing key features of the minority class, SMOTE enhances the accuracy of predictions and overall model performance.

<img width="491" height="638" alt="Screenshot 2026-06-09 at 4 35 39 PM" src="https://github.com/user-attachments/assets/e079dba1-a6ab-49c8-a0ed-49bb8dd4dd5e" />


Screen Shot 2024-08-05 at 1.37.54 AM.png
Purpose: Develop a classifier to predict fraudulent transactions.
Data Source: Kangle.
Steps:

         - Data preparation.

         - Feature extraction.

         - Model prediction.

         - Conclusion and Plan to improve prediction.

​Technical Skills: 

         - Analyze the variance of feature distributions.

         - Eliminate duplicate rows.

         - Fill the missing value rows by "Mean."
         - Analyze correlations between variables.
         - Split data and handle imbalanced problem by SMOTE method.

         - Implement Principle Component Analysis (PCA).

         - Implement K_fold_test function.

         - Develop Modeling Prediction.

         - Evaluate a given model using cross-validation.

         - Evaluate the models and store results.

         - Visualize model performance for comparison.

Data Preprocessing
The data learning phase
Building Functions
Screen Shot 2024-08-05 at 7.44.36 PM.png
The Correlation Matrix
Screen Shot 2024-08-05 at 7.59.21 PM.png
Correlation Matrix Interpretation 

1. Significant Positive Correlations:
   - Unique Sent To Addresses and Unique Received From Addresses: Strong positive correlation of 1.
   - Max value received and avg val received: Correlation of 0.62.
   - Max val sent and avg val sent: Correlation of 0.6.
   - ERC20 uniq rec addr and ERC20 uniq sent addr: Correlation of 0.73.
   - ERC20 uniq rec addr and ERC20 uniq sent addr.1: Correlation of 0.57.
2. Significant Negative Correlations:
   - FLAG and Time Diff between first and last (Mins): Correlation of -0.22, indicating that as the FLAG value increases, the time difference between the first and last transactions tends to decrease.
3. Other Observations:
   - Features related to values (e.g., max value received, avg val received, max val sent, avg val sent) show moderate positive correlations among themselves.
   - ERC20-related features (e.g., ERC20 uniq rec addr, ERC20 uniq sent addr, ERC20 uniq sent addr.1) show positive correlations with each other, indicating some degree of relationship among these features.
4. Importance:
   - Feature Selection: Highly correlated features might provide redundant information. Depending on the use case, it might be beneficial to select only one of the highly correlated features to reduce multicollinearity in the model.
   - Model Insights: Understanding correlations helps in interpreting model predictions and ensuring the robustness of the model.
5. Next Steps:

    - Detect Multicollinearity by VIF.
    - Address Multicollinearity: Consider techniques such as Principal Component Analysis (PCA) or removing some of the highly correlated features.

 Principal Component Analysis (PCA)

Certainly, the maximum values and averages demonstrate a strong correlation. Similarly, the number of ERC20 token transactions sent to unique account addresses (ERC20UniqSent_Addr) and the number of ERC20 token transactions received from unique addresses (ERC20UniqRec_Addr) also show high correlation. However, there is no significant multicollinearity among the features.
I utilized Principal Component Analysis (PCA) to potentially enhance the performance of an XGBoost binary classifier, though its effectiveness varies based on the specifics of your dataset and problem. PCA can impact your XGBoost model in several ways: Dimensionality Reduction, Noise Reduction, Improved Training Speed, Feature Engineering.

Screen Shot 2024-08-06 at 12_edited.jpg
Illustration sourced from site

Extracting Data Phase
1656 Fraud and 7632 Non_Fraud
17.829 Fraud and 82.171 Non_Fraud

Screen Shot 2024-08-05 at 7.51_edited.jp
I used the SMOTE technique to address the imbalance issue when splitting the data into training and testing sets.

In this problem, I observe that in Ethereum trading, there are 1,656 fraudulent transactions and 7,632 non-fraudulent ones. This means the dataset is imbalanced, with only 17.829% of transactions being fraudulent. A simple binary classifier might achieve a high accuracy of 82.171% by predicting most transactions as non-fraudulent. However, in such skewed class distributions, accuracy is not a reliable metric.

Imbalanced datasets are a common challenge in binary classification problems, often seen in practical applications like fraud detection, spam filtering, rare disease identification, and hardware fault detection. One effective technique to address this issue is the Synthetic Minority Oversampling Technique (SMOTE). SMOTE generates synthetic samples for the minority class, helping to balance the dataset.

The significance of SMOTE lies in its ability to handle class imbalance, thereby improving the performance of classifier models. By reducing bias and capturing key features of the minority class, SMOTE enhances the accuracy of predictions and overall model performance.

Modeling Prediction
Approached Predictive Modeling
Screen Shot 2024-08-06 at 12.37.31 AM.png
Definition of predictive Models
The stacking model, which combines the outputs of multiple models and processes them through another machine learning model known as a meta-learner. The model functions by taking the outputs of several statistical models (such as linear regressors/classifiers, KNN, CART, SVM, and Bayesian models) and feeding them into a meta-learner, typically a logistic regression model. The meta-learner's goal is to minimize the weaknesses and enhance the strengths of each individual model. This often results in a highly robust model that generalizes well to unseen data.

​

K-Nearest Neighbors (KNN) is a straightforward, non-parametric, and lazy learning algorithm suitable for both classification and regression tasks. It functions by finding the k closest data points in the training dataset to a new input data point and making predictions based on these nearby points. In classification, the predicted class is determined by the most common class among the k neighbors. In regression, the predicted value is calculated as the average of the values of the k nearest neighbors. KNN is easy to understand and implement, but its performance heavily depends on the choice of k and the distance metric used. Furthermore, KNN can be computationally demanding and slow with large datasets because it requires calculating distances between the input point and all training data points.

​

Linear regression is a statistical method used to understand the relationship between a dependent variable and one or more independent variables by fitting a linear equation to the data. The objective is to identify the line (or plane in multiple dimensions) that best matches the data by minimizing the differences between the predicted and actual values. For simple linear regression, the model is represented as
Y = β0 + β1X + ϵ where Y is the dependent variable, X is the independent variable, β0 is the y-intercept, β1 is the slope of the line, and ϵ denotes the error term. In multiple linear regression, the model includes multiple independent variables. Although linear regression is valued for its simplicity and ease of interpretation, it relies on the assumption of a linear relationship and may not be effective if the relationship is non-linear or if there are substantial outliers.

​

Classification and Regression Trees (CART) is a decision tree technique used for both classification and regression tasks. The model operates by recursively dividing the data into subsets according to feature values, forming a tree-like structure where each node signifies a decision rule. In classification tasks, CART determines the class of an input by navigating through the tree's branches, with the leaves indicating the final class predictions. For regression tasks, the model estimates a continuous value by averaging the target variable within the terminal nodes. While CART is simple and easy to interpret, it is prone to overfitting, particularly with intricate trees. To mitigate overfitting and enhance the model's ability to generalize, pruning methods are commonly employed.

​

​Support Vector Machine (SVM) modeling is a supervised learning model used for classification and regression tasks. It works by finding the optimal hyperplane that best separates different classes in the feature space, maximizing the margin between the closest data points of each class. For classification, SVM aims to identify this hyperplane to ensure the greatest separation between the classes. In cases where data is not linearly separable, SVM can use kernel functions to transform the feature space, enabling the separation of classes in a higher-dimensional space. For regression tasks, SVM attempts to fit the best line within a specified margin of tolerance. SVM is effective for complex and high-dimensional data but can be computationally intensive and sensitive to the choice of hyperparameters and kernel functions.

​

XGBoost (Extreme Gradient Boosting) is a advanced machine learning algorithm designed for high-performance classification and regression tasks. It extends the gradient boosting framework by using decision trees as base models and applies boosting techniques to improve predictions incrementally. XGBoost adds trees sequentially to address errors from previous trees, enhancing the model's accuracy. It includes regularization methods to reduce overfitting, making the model more robust and effective in generalizing to new data. Known for its efficiency and scalability, XGBoost can manage large datasets and complex problems with ease. Additionally, it offers extensive hyperparameter tuning options to optimize its performance for various data scenarios.

​

I also evaluate model performance using RepeatedStratifiedKFold cross-validation, a technique specifically designed for classification tasks. This method integrates stratified sampling with repeated cross-validation. Stratified sampling ensures that each fold maintains the same class distribution as the entire dataset, preserving class balance in both training and validation sets. Repeated cross-validation involves dividing the data into k folds and repeating the process n times, each with different splits. This approach delivers a more thorough assessment of the model’s accuracy and stability by averaging results across multiple iterations. By applying this technique, I achieve a more reliable evaluation of model performance across various data subsets.

Selected predictive model
When evaluating model performance, both XGBoost and stacking demonstrate high accuracy. Among these, XGBoost provides several advantages over stacking, especially in terms of performance and efficiency. It employs gradient boosting to iteratively refine predictions, achieving excellent accuracy and speed with lower computational cost. XGBoost is particularly adept at handling complex datasets with non-linear relationships, making it suitable for large-scale problems. Additionally, it integrates built-in regularization and feature selection, which help prevent overfitting and ease model tuning. In comparison, stacking involves combining multiple base models and a meta-model, which can be more resource-intensive and complex to manage. Although stacking can enhance performance by integrating diverse models, XGBoost's efficient and streamlined approach often leads to faster and more straightforward implementations.

<img width="459" height="811" alt="Screenshot 2026-06-09 at 4 36 12 PM" src="https://github.com/user-attachments/assets/f02b5c93-5517-4624-813d-6c091b30daf6" />

<img width="910" height="815" alt="Screenshot 2026-06-09 at 4 38 05 PM" src="https://github.com/user-attachments/assets/6f60a595-c12d-48fb-8538-30bc6c7c1451" />

<img width="895" height="299" alt="Screenshot 2026-06-09 at 4 38 30 PM" src="https://github.com/user-attachments/assets/ebd206c1-09e7-4f2d-a46f-02b4ca97f8c9" />

                                                      Conclusion
The XGBoost model performs well with high accuracy, precision, recall, and F1-score. It effectively distinguishes between fraudulent and non-fraudulent transactions, especially with a high true positive rate and a low false positive rate.

Next Steps to Improve Prediction
Feature Engineering:
Identify and create new features that might better capture the nuances of fraudulent transactions.
Use domain knowledge to add or modify features.
Hyperparameter Tuning:
Experiment with different hyperparameters of the XGBoost model to find an optimal set that improves performance.
Techniques like Grid Search or Random Search can be helpful.

Algorithm Tuning:
Experiment with Different Algorithms: Try other powerful algorithms like CatBoost or Neural Networks.
Parameter Tuning in XGBoost: Continue to tune parameters such as learning_rate, max_depth, min_child_weight, gamma, subsample, and colsample_bytree.







