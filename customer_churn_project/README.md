## Bank customer churn prediction

### Project summary
Beta Bank has been losing customers every month. In this project, I build a binary classification model to predict whether a customer will leave the bank in the near future, using historical behavioural and contract data.

**Goal:** maximise **F1-score** (minimum required: **0.59**)  
**Additional metric:** **ROC AUC**

### Key results
- Best model: **Random Forest** with **class_weight='balanced'**
- Test metrics:
  - **F1 = 0.645**
  - ROC AUC = 0.868
  - Accuracy = 0.855
  - Precision = 0.642
  - Recall = 0.649
- Class imbalance detected (~1:4) and addressed using three approaches:
  - class weighting (best)
  - undersampling
  - oversampling
- Sanity check: compared against a constant baseline model (predicting the majority class).
- Feature importance analysis confirmed earlier EDA assumptions (e.g., customer age and number of bank products were among the most influential factors).

### Workflow
1. Data exploration and EDA
2. Data preprocessing
3. Train/valid/test split (with stratification)
4. Baseline models without imbalance handling
5. Hyperparameter tuning with **GridSearchCV**
6. Handling class imbalance:
   - class weights
   - undersampling
   - oversampling
7. Final evaluation on the test set

### Tech stack
Python, pandas, NumPy, scikit-learn, matplotlib, seaborn

<details>
  <summary><b>Final model parameters (Random Forest)</b></summary>

  - bootstrap: True  
  - ccp_alpha: 0.0  
  - class_weight: 'balanced'  
  - criterion: 'gini'  
  - max_depth: None  
  - max_features: 'sqrt'  
  - max_leaf_nodes: None  
  - max_samples: None  
  - min_impurity_decrease: 0.0  
  - min_samples_leaf: 4  
  - min_samples_split: 2  
  - min_weight_fraction_leaf: 0.0  
  - n_estimators: 100  
  - n_jobs: None  
  - oob_score: False  
  - random_state: 12345  
  - verbose: 0  
  - warm_start: False  

</details>
