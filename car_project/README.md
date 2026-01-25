# Car Price Prediction Project

(Notebook is currently in Russian; English version in progress)

### **Task**

Build a model to estimate a car’s market price. The final model is chosen based on:
- prediction quality (the main metric is RMSE);
- prediction speed (inference time);
- training time.


  
### **Data**

We use historical data containing car technical specifications, configurations (trim/options), and prices.

The dataset is stored in autos.csv.



### **Project plan**

- Load and inspect the data
- Data analysis and preprocessing
- Train several models and tune hyperparameters
- Compare models by quality (RMSE) and runtime (training + inference)
- Conclusions



### **Libraries used**
- pandas
- numpy
- seaborn
- matplotlib
- re
- time
- sklearn
- catboost
- lightgbm
- warnings



### **Conclusions**
    
- Trained four models: Linear Regression, Random Forest, CatBoost Regressor, and LightGBM Regressor.
- Selected and tuned the best hyperparameters for each model.
- Evaluated the tuned models on the test set.
- Compared models by RMSE, training time, and prediction speed.
- Performed a sanity check by comparing model performance with a constant (baseline) predictor.
- The lowest test RMSE = 1487.79 was achieved with LightGBM Regressor.
- Linear Regression was the fastest, but its prediction quality was significantly worse than the other models.
- LightGBM Regressor provided the best overall trade-off between accuracy and runtime.
- Recommendation: Use LightGBM Regressor as the final model.
