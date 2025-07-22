# 🚀 Startup Scoring Model

This project is focused on ranking startups based on various business metrics using a scoring algorithm and machine learning models for evaluation.

##  Objective
To build a robust and optimized model that ranks startups using multiple business indicators such as market size, user base, burn rate, and team experience — even without a target variable. The goal is to create a scoring system that reflects a startup's health and potential.

##  Approach

### 1. Data Preprocessing & Cleaning
- Loaded the dataset and checked for nulls and datatypes.
- Normalized the numerical features to bring all values into the same scale.

### 2. Feature Weighting using PCA
Used **Principal Component Analysis (PCA)** to determine which features contribute most to the variance in the dataset. This ensured objective, data-driven weight assignments.

**PCA-Based Feature Weights:**
- `team_experience`: **22.4%**
- `market_size_million_usd`: **21.3%**
- `monthly_active_users`: **17.3%**
- `monthly_burn_rate_inr`: **16.3%**
- `funds_raised_inr`: **11.4%**
- `valuation_inr`: **11.2%**

### 3. Handling Negatively Correlated Features (Burn Rate)
Burn rate is negatively correlated — higher burn is worse.  
So, we inverted it using the formula:  
inverted_burn = 1 - normalized_burn
This aligns all features to the "higher is better" direction.

### 4. Startup Scoring
A weighted sum of the normalized features was used to calculate a final score for each startup. This score was then used to rank them.

### 5. Evaluation Metrics & Bonus Modeling(Additional)
To test the scoring, we trained regression models using the score as the target.

####  Linear Regression:
- **RMSE**: 0.0000
- **MAE**: 0.0000
- **R²**: 1.0000

#### 🌲 Random Forest Regressor:
- **RMSE**: ~6.95
- **MAE**: ~5.37
- **R²**: ~0.72

This shows that the score captures meaningful variance and patterns.

## 📈 Visuals
All visualizations (bar charts, histograms, heatmaps, etc.) are rendered directly in the Jupyter notebook. These help explain the PCA, feature importance, and score distributions clearly.

## 💡 Insights & Observations

- Startups with **strong team**, **large market**, and **high user base** ranked higher — which aligns with real-world startup evaluation.
- High funding or valuation alone didn't guarantee a high score.
- Low burn rate significantly helped improve rankings.

## 🚀 Future Improvements
- Use **real-world startup datasets** from platforms like Crunchbase or AngelList.
- Add features like **revenue**, **growth rate**, **team size**, etc.
- Use **SHAP values** or **feature importance plots** for interpretability.
- Try unsupervised clustering to identify startup segments.


BY RAHUL S
