# ClubMahindraDataOlympics
Solution for Club Mahindra Data Olympics Hackathon

# 1. Feature Extraction and Engineering
   Generated 5 different sets of features:
   
   a. 45 Features with features extracted from dates, total_pax, number of childrens and adults.
   
   b. Added more date based features to get 75 features.
   
   c. OneHotEncoded the above features to obtain a new data with 252 features
   
   d. Added more features obtained from memberid based on linking each feature to memberid and extracting the relations
   
   e. Obtained a fresh set of pandas category features along with usual numerical features to be used for training lightgbm and catboost by passing the cat features explicitly, so that the underlying algorithms handle the cat features on their own.
   

# 2. Cross Validation and Parameter Tuning
   Used groupfold on the memberid so that no two folds contain same memberid instances. Used 5 fold and 10 fold cv to hyperparameter tune various first level models in the final stacked model. Also used the same cv to tune 2nd level models.

# 3. Stacking Model
   ## a. First Layer Models
   The first level models were trained on the 5 different dataset features. Used various first level models including RF, XGBoost, LightGBM, CatBoost, AdaBoost, GradientBoosting, SGDRegressor, MLPRegressor, etc.

   ## b. Second Layer Models
   Used three models in the second level including XGBoost, LightGBM and SGDRegressor.

   ## c. Thirst Layer Model:
   The final layer was a simple averaging of the predictions of the second layer.

# 4. Submission
   To replicate the submission create three folders in the working directory, namely, "freshPickles", "rsp" and "submission". Execute the jupyter notebooks featureEngineering1.ipynb, featureEngineering2.ipynb and featureEngineering3.ipynb. Finally execute the notebook finalStacking.ipynb.
