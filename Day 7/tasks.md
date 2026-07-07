# Day 7 Tasks

**Dataset & algorithms — important:** For every task below use the same dataset you used for your Day 6 project (your own project dataset). Do not swap to a different dataset or re-split the data. Use the algorithms you have chosen for your project and perform hyperparameter tuning with `RandomizedSearchCV` where requested.

## 1. Compute full evaluation metrics for your Day 6 model (Specific to your project)
**What this means:** Yesterday you built a model and looked at a few predictions. Today, calculate an overall "grade" for how the model performed on the full test set from your project dataset.
**What to do:** 
- **Classifiers (predicting categories):** Print the `classification_report(y_test, y_pred)` — Accuracy, Precision, Recall, and F1-score for each category.
- **Regressors:** Calculate RMSE, MAE, and R² on `y_test` / `y_pred`.
- **Anomaly Detection:** Report the number of anomalies detected versus actual anomalies.
- **Similarity/Recommendation:** Inspect the top-5 recommendations for 3 sample inputs and comment on quality.

## 2. Plot a confusion matrix or residual plot (Specific to your project)
**What this means:** Visualize model mistakes to understand failure modes.
**What to do:** 
- **Classifiers:** Plot a labeled confusion matrix heatmap (`seaborn.heatmap(confusion_matrix(y_test, y_pred), annot=True)`); for multi-class include normalized percentages.
- **Regressors:** Plot actual vs predicted values with a diagonal reference line; save as `residual_plot.png`.
- Save your plot as `confusion_matrix.png` or `residual_plot.png` in your project folder.

## 3. Train a second comparison algorithm (Specific to your project)
**What this means:** Train at least one additional algorithm (a different model family) using the same `X_train` and `y_train` from your project dataset. This will be your baseline or challenger model.
**What to do:** 
- Choose an algorithm different from your Day 6 model (e.g., if Day 6 was a tree, try an SVM or a linear model, or vice versa).
- Use the exact same preprocessing pipeline and the same `X_train`/`X_test` splits — do not re-split or re-preprocess.

### 3a. Hyperparameter tuning with RandomizedSearchCV (Required)
**What this means:** For the models you have chosen (both your Day 6 model and the comparison algorithm), run `RandomizedSearchCV` to find better hyperparameters before comparing final scores.
**What to do:**
- Create a parameter distribution (`param_distributions`) appropriate for each algorithm you selected.
- Use `RandomizedSearchCV(estimator, param_distributions, n_iter=20, cv=5, scoring=..., random_state=42, n_jobs=-1)` and choose `scoring` according to your task (`'accuracy'` or `'f1_weighted'` for classifiers, `'neg_root_mean_squared_error'` or `'neg_mean_squared_error'` for regressors).
- Fit the `RandomizedSearchCV` on `X_train` / `y_train` and record `best_estimator_`, `best_params_`, and cross-validated score.
- After tuning, evaluate the selected `best_estimator_` on your `X_test` / `y_test` and produce the final predictions to be used in Steps 1–5.
- Save tuned models as `modelname_random_search.pkl` using `joblib.dump()`.

## 4. Build a side-by-side comparison DataFrame (Universal for everyone)
**What this means:** Compare final tuned models (Day 6 tuned model and the challenger tuned model) using the same test set.
**What to do:** 
- Create a pandas `DataFrame` where rows are model names and columns are the evaluation scores from Step 1 (e.g., Accuracy, Precision (weighted), Recall (weighted), F1 for classifiers; RMSE, MAE, R² for regressors).
- Save this table as `comparison.csv` and add a notebook markdown cell stating which model wins and *why* using the metrics.

## 5. Save the winning model as best_model.pkl (Universal for everyone)
**What this means:** Save the final chosen model and any preprocessing objects so your app can load them later.
**What to do:** 
- Choose the better-performing tuned model from the comparison table.
- Save it with `joblib.dump(model, 'best_model.pkl')` and also save any scaler/encoder/pipeline objects used in production.
- Print the chosen model's name and its final test score in your notebook.

## Notes & tips
- Keep your random seed stable (`random_state=42`) so results are reproducible.
- When using `RandomizedSearchCV`, tuning ranges matter more than exact values; prefer broader distributions and fewer iterations for complex models.
- If your dataset is imbalanced, prefer stratified CV (`StratifiedKFold`) and use appropriate scoring (e.g., `f1_weighted` or class-specific metrics).



*Colab Link:* https://colab.research.google.com/drive/1rC5UxK1aNfNNWomAH5vQcu_Qszuzv6Gl?usp=sharing