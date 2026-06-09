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

