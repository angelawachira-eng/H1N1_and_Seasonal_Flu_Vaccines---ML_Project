# **VACCINES PREDICTION ANALYSIS**

![thumbnail](https://github.com/user-attachments/assets/2233c19c-9dee-46a0-a0f7-57bf22d3fea1)

PROJECT OVERVIEW

This project leverages machine learning to predict whether individuals received the H1N1 and Seasonal flu vaccines based on behavioral survey data from the National 2009 H1N1 Flu Survey. By identifying the key drivers of vaccination, this analysis provides actionable insights for public health officials to improve future immunization campaigns.

## 2. Business and Data Understanding
*   **Stakeholder:** Public Health Departments and Vaccination Campaign Managers.
*   **Business Problem:** How can we accurately identify and target individuals who are likely to opt out of vaccination to prioritize educational outreach?
*   **Dataset:** 26,707 survey responses encompassing 35 categorical and numerical features including doctor recommendations, personal opinions on vaccine effectiveness, and demographic indicators.

## 3. Modeling
This analysis employed an **Iterative Modeling Approach** to benchmark progression:
1.  **Baseline Logistic Regression:** Proved a strong linear baseline but struggled with H1N1 class imbalance.
2.  **SMOTE Logistic Regression (H1N1 Champion):** Utilized Synthetic Minority Over-sampling to prioritize **Class 1 Recall (71%)**, successfully identifying the majority of vaccinated patients.
3.  **Decision Tree:** Explored non-linear relationships but suffered from overfitting on synthetic training data.
4.  **Random Forest (Seasonal Champion):** An ensemble model that stabilized predictive variance, achieving **78% Accuracy** and **~77% Recall** on naturally balanced data.

## 4. Evaluation
Models were evaluated using **Recall for Class 1 (Vaccinated)** as the primary success metric to capture as many "Yes" cases as possible.
*   **H1N1 Results:** The **SMOTE Logistic Regression** outperformed all other models in identifying the 21% minority vaccinated group.
*   **Seasonal Results:** The **Random Forest** achieved the highest overall reliability and model confidence.
*   **ROC Curve Analysis:** Proved a solid mathematical ceiling for the dataset around **0.83 - 0.85 AUC**, indicating high discriminative power for health-related behavior.

## 5. Conclusion & Recommendations
The analysis identified **Doctor Recommendations** and **Perceived Personal Risk** as the two most powerful mathematical predictors of vaccine uptake.

### Key Recommendations:
1.  **Prioritize Doctor-to-Patient Outreach:** Since a recommendation is the highest-weighted feature, campaigns should focus on empowering physicians with localized advocacy tools.
2.  **Target Perceived "Low Risk" Populations:** The model identifies these individuals as the highest-probability group for non-vaccination; educational digital ads should target this cognitive bias.
3.  **Aggressive H1N1 Normalization:** Because H1N1 uptake (21%) is less than half of Seasonal flu (47%), public funding must be weighted specifically toward H1N1 normalization and accessibility.
