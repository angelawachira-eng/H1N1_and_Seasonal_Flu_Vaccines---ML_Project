# **VACCINES PREDICTION ANALYSIS**

![thumbnail](https://github.com/user-attachments/assets/2233c19c-9dee-46a0-a0f7-57bf22d3fea1)

1. Project Overview
   
This project leverages machine learning to predict whether individuals received the H1N1 and Seasonal flu vaccines based on behavioral survey data from the National 2009 H1N1 Flu Survey. By identifying the key drivers of vaccination, this analysis provides actionable insights for public health officials to improve future immunization campaigns.


### 2. BUSINESS PROBLEM

Public health organizations often face challenges in achieving high vaccination rates due to differences in individuals’ beliefs, behaviors, and access to healthcare. Without a clear understanding of these factors, it is difficult to design effective vaccination campaigns and allocate resources efficiently.

The goal of this project is to predict the likelihood that individuals received the H1N1 and seasonal flu vaccines, by estimating two probabilities: one for h1n1_vaccine and one for seasonal_vaccine. By identifying individuals who were less likely to have been vaccinated and understanding the factors influencing their decisions, stakeholders can implement targeted interventions, improve vaccine uptake, and reduce the spread of infectious diseases.
## 3. Business and Data Understanding
### Stakeholder and Problem
The primary stakeholder for this project is the **Public Health Department** tasked with maximizing vaccine coverage. The goal is to accurately identify and target individuals who are likely to opt out of vaccination to prioritize educational outreach.

### Research Objectives & Key Findings
*   **Which vaccine is most effective?** In terms of public adoption, the **Seasonal Vaccine (46.56%)** reached a significantly larger audience than the H1N1 (21.25%).
*   **What are the key factors?** Analysis proved that **Doctor Recommendations** and **Perceived Personal Risk** are the two strongest predictors of someone choosing to vaccinate.
*   **Joint Probabilities:**
    *   **Probability of receiving Both Vaccines:** 17.59%
    *   **Probability of receiving Either Vaccine:** 50.22%
    *   **Probability of receiving Neither Vaccine:** 49.78%
*   **Decision-Making:** The project demonstrates that using **Logistic Regression (for H1N1)** and **Random Forest (for Seasonal)**, public health officials can prioritize outreach to individuals based on their "predicted probability" of vaccination.

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

## 5. Final Recommendations
1.  **Prioritize Doctor-to-Patient Outreach:** Since a recommendation is the highest-weighted feature, campaigns should focus on empowering physicians with localized advocacy tools.
2.  **Target Perceived "Low Risk" Populations:** The model identifies these individuals as the highest-probability group for non-vaccination; educational digital ads should target this cognitive bias.
3.  **Aggressive H1N1 Normalization:** Because H1N1 uptake is less than half of Seasonal flu, public funding must be weighted specifically toward H1N1 normalization and accessibility.

