Advanced Time Series Forecasting Project

Overview
This project demonstrates advanced time series forecasting using Facebook Prophet, external regressors, and hyperparameter optimization with Optuna.  
A synthetic dataset is generated to simulate real-world scenarios with trend, seasonality, marketing spend, and macroeconomic indicators.  
The workflow includes baseline modeling, optimized forecasting, performance comparison, and cross-validation.

---

Features
- Synthetic dataset creation with trend, weekly, yearly seasonality, and external regressors.
- Baseline Prophet model vs Optimized Prophet model.
- Hyperparameter tuning using Optuna.
- Performance evaluation with MAE, RMSE, MSE.
- Cross-validation and metrics reporting.
- Clear visualizations comparing actual vs forecasted values.

---
Requirements
Install dependencies before running the notebook:

`bash
pip install prophet scikit-learn optuna matplotlib pandas numpy
`
---
Workflow
1. Generate Synthetic Dataset  
   - Trend, weekly, yearly seasonality  
   - External regressors: marketing spend, macro index  

2. Train-Test Split  
   - Last 365 days reserved for testing  

3. Baseline Prophet Model  
   - Without external regressors  
   - Metrics: MAE ≈ 7.38, RMSE ≈ 9.42  

4. Prophet with External Regressors  
   - Adds marketing spend & macro index  

5. Hyperparameter Optimization (Optuna)  
   - Tuned changepointpriorscale and seasonalitypriorscale  
   - Best params:  
     `json
     {
       "changepointpriorscale": 0.0115,
       "seasonalitypriorscale": 1.5043
     }
     `

6. Optimized Prophet Model  
   - Metrics: MAE ≈ 4.01, RMSE ≈ 5.01  
   - Significant improvement over baseline  

7. Cross Validation  
   - Horizon: 365 days  
   - Metrics: MSE, RMSE, MAE, MAPE, SMAPE  

8. Visualization  
   - Forecast vs Actual plot  
   - Performance metrics table  

---

 Results
| Model      | MAE   | RMSE  |
|------------|-------|-------|
| Baseline   | 7.38  | 9.42  |
| Optimized  | 4.01  | 5.01  |

---
Conclusion

This project successfully demonstrates how advanced time series forecasting can be enhanced by incorporating external regressors and hyperparameter optimization.  

- The baseline Prophet model provided a reasonable forecast but with higher error values (MAE ≈ 7.38, RMSE ≈ 9.42).  
- By adding marketing spend and macro index as regressors, and tuning hyperparameters with Optuna, the optimized model achieved a substantial improvement (MAE ≈ 4.01, RMSE ≈ 5.01).  
- Cross-validation confirmed the robustness of the optimized model across multiple horizons, showing consistent accuracy and coverage.  
- Visualizations highlighted how closely the optimized forecast aligned with actual values, validating the effectiveness of the approach.
