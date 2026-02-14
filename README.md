# MSCS 634 – Project Deliverable 3 
## Classification, Clustering, Pattern Mining

---

## Running Instructions

1. Place the dataset files in the same directory as the notebook.
2. Open the notebook in Jupyter/Colab/VS Code.
3. Execute the cells from top-to-bottom.
4. If the Apriori does not work, you need to install mlxtend:
pip install mlxtend

--- 

## Requirements 

pip install --user mlxtend

We needed mlxtend because it provides extra tools for advanced data mining—like Apriori association rules, frequent itemset mining, and stacking classifiers—which aren’t in standard libraries. Without it, your project scripts that use these functions would fail.

---

## Introduction

The purpose of this project is to utilize the healthcare stroke dataset for the completion of the three major tasks of classification, clustering, and association rule mining. The objective of this project is to learn useful patterns in the patient's data, and to provide examples of how these patterns can be utilized in real-world applications.

--- 

### Key Findings

### 1) Classification (Stroke Prediction)
- Two classification models were created to predict stroke where 0 = No, 1 = Yes.
- Evaluation metrics included Accuracy, F1-score, Confusion Matrix, and ROC Curve.
- F1-score and ROC-AUC were key because the stroke class is small and the data is imbalanced. 
- Hyperparameter tuning was used to improve model performance and generalization. 
- **Key Insight:** Classification models can help identify individuals who have a higher likelihood of experiencing a stroke, therefore enabling them to receive earlier attention and prevention efforts.
 
### 2) Clustering (Grouping Similar Patients)
- K-Means clustering model was developed to group patients into clusters based on similar characteristics.
- Silhouette Score was used to determine the optimal number of clusters.
- PCA was utilized to visualize clusters in 2D for better comprehension.
- Cluster Profiling such as mean values for age, BMI, glucose, hypertension provided an overview of each cluster.
- **Key Insight:** Clustering enables the creation of patient subgroups, such as “high-risk” vs “low-risk,” which will enable targeted healthcare programs and the allocation of resources more effectively.
 
### 3) Pattern Mining 
- Apriori was employed to generate frequent itemsets and association rules by utilizing support, confidence, and lift.
- Rules revealed common combinations of risk factors like hypertension + smoking + high glucose that correlate with stroke outcomes.
- **Key Insight:** Association rules can help reveal “if-then” patterns that are easy to comprehend. Such patterns are helpful for promoting awareness, guiding prevention plans, and educating patients about their risks.

---

## Real-World Applications
- Hospitals/Clinics: Models can help identify high-risk patients and facilitate early screening.
- Doctors/Healthcare Teams: Rules and patterns of risk can serve as a tool for decision-making.
- Public Health: Clusters and rules can inform public health educational campaigns targeting groups with higher levels of risk behaviors or conditions.
- Patient Education: Patterns of “if-then” are simple to communicate to patients and can help them understand why prevention is essential.

---

## Challenges Encountered and Solutions Implemented

--- 

### 1) Class Imbalance (Stroke = 1 is Rare)
- Challenge: The stroke dataset contains many “No stroke” cases and relatively few “Stroke” cases making accuracy unreliable.
- Solution: We used F1-score and ROC-AUC to evaluate the models and employed `class_weight="balanced"` to encourage the models to learn the minority class better.
### 2) Missing Package for Apriori
- Challenge: The Apriori code required `mlxtend` and some environments did not have it installed.
- Solution: We installed it using: pip install mlxtend and then we restarted the kernel and ran the notebook again.
### 3) Selecting Significant Rules
- Challenge: Some rules can be overly frequent or weak if the threshold settings for support, confidence, and lift are inadequate.
- Solution: We modified the thresholds for support, confidence, and lift to only retain meaningful rules.


