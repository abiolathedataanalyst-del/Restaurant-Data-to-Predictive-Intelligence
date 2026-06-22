# 🍽️ The Palate Predictor: Unveiling the Secrets Behind Restaurant Ratings

> *A Data-Driven Journey to Understand Culinary Success*

---

## 📌 Project Overview

In the competitive world of gastronomy, understanding what drives restaurant success — particularly through customer ratings — is invaluable intelligence for operators, investors, and platform strategists alike.

This project undertakes an end-to-end data science workflow on the **Zomato restaurant dataset**, spanning multiple countries and culinary categories. Starting from raw, unprocessed data, the analysis progresses through systematic cleaning, exploratory analysis, advanced feature engineering, and ultimately machine learning-powered prediction of restaurant aggregate ratings.

The central objective is to decode the **"secret sauce"** — the quantifiable factors that differentiate a top-rated restaurant from an average one — and deliver actionable intelligence to stakeholders in the food and hospitality industry.

---

## 🛠️ Tools & Technologies Used

| Category | Tools / Libraries |
|---|---|
| **Language** | Python 3.x |
| **Data Manipulation** | Pandas, NumPy |
| **Data Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-learn (Linear Regression, Random Forest Regressor) |
| **Feature Engineering** | KMeans Clustering (Geolocation), LabelEncoder, StandardScaler |
| **Data Export** | OpenPyXL (Excel output) |
| **Development Environment** | Jupyter Notebook |

---

## ❓ Key Business Questions

This project was structured around five core analytical questions:

1. **What is the general distribution of restaurant ratings?** — Are most restaurants rated well, poorly, or somewhere in the middle?
2. **Which cities and cuisines dominate the restaurant landscape?** — Where are the culinary hubs, and what food types lead in volume?
3. **Does online delivery or table booking influence customer ratings?** — Do convenience features correlate with higher satisfaction?
4. **Does price correlate with quality?** — Do more expensive restaurants consistently earn higher ratings?
5. **What are the strongest predictors of a restaurant's aggregate rating?** — Which factors — votes, location, cuisine, cost — matter most in a predictive model?

---

## 📊 Dashboard Overview

The analytical workflow is structured across seven chapters within the notebook:

### Chapter 1 — Raw Ingredients: Data Loading & Initial Inspection
Initial dataset profiling including shape, data types, descriptive statistics, and missing value identification. The dataset contained missing values primarily in the `Cuisines` column.

### Chapter 2 — Kitchen Prep: Data Cleaning & Preprocessing
- Filled missing cuisine values with `'Unknown'`
- Removed duplicate records
- Standardized column names (lowercased, underscored)

### Chapter 3 — The Grand Tasting: Exploratory Data Analysis (EDA)
Five core visual analyses:
- **Rating Distribution** — Histogram showing moderate clustering with few extremes
- **Top 10 Cuisines** — Bar chart of culinary frequency dominance
- **Top 10 Cities** — Bar chart highlighting Delhi, Gurgaon, and Noida as major hubs
- **Online Delivery vs. Rating** — Boxplot examining delivery-rating correlation
- **Price Range vs. Rating** — Boxplot exploring cost-quality relationship

### Chapter 4 — Recipe Enhancement: Feature Engineering
Four engineered features added predictive depth:
- **Cuisine Dummies** — One-hot encoded cuisine flags per restaurant
- **Restaurant Density & Locality Average Rating** — Contextual neighbourhood metrics
- **Standardized USD Cost** — Multi-currency normalization using real exchange rates, categorized as Cheap / Moderate / Expensive
- **Geolocation Clusters** — KMeans clustering (k=5) on latitude/longitude coordinates

### Chapter 5 — The Predictive Model: Machine Learning
Two regression models trained on 80/20 train-test split with StandardScaler normalization:
- Linear Regression (baseline)
- Random Forest Regressor (primary model, 100 estimators)

### Chapter 6 — The Verdict: Model Evaluation
Performance metrics computed on the Random Forest model against the held-out test set.

### Chapter 7 — The Secret Sauce: Feature Importance Analysis
Bar chart of feature importances from the Random Forest model, ranking the relative contribution of each predictor to the final rating.

---

## 💡 Key Insights

### 1. Rating Distribution is Normally Concentrated
The majority of restaurants cluster around moderate aggregate ratings, with genuinely excellent (4.5+) and genuinely poor (below 2.0) establishments being statistical outliers. This suggests a market where differentiation at the top is driven by specific, identifiable factors rather than general quality variance.

### 2. Delhi, Gurgaon, and Noida Dominate Listing Volume
Indian metropolitan cities — particularly those in the NCR region — account for the largest share of restaurant listings. This geographic concentration signals both market saturation and high consumer demand in urban India.

### 3. Online Delivery Correlates with Higher Ratings
Restaurants offering online delivery tend to achieve higher median ratings compared to those that do not. This suggests that convenience-oriented services positively influence overall customer perception, potentially reflecting modern consumer preferences.

### 4. Higher Price Range Yields Marginally Higher Ratings — But Not Decisively
While restaurants in higher price bands tend to show slightly elevated ratings, the variance within each price tier is significant. Quality dining experiences exist across all price points, confirming that price is not a reliable proxy for quality.

### 5. The Model Achieved an R² of 0.964 (RMSE: 0.287)
The Random Forest Regressor demonstrated exceptional predictive accuracy, explaining 96.4% of the variance in aggregate ratings. This validates the feature engineering approach and confirms that rating outcomes are largely quantifiable from available restaurant attributes.

### 6. Customer Engagement (Votes) is the Dominant Predictor
The volume of votes a restaurant receives is by far the most important feature in the model. High vote counts reflect strong community engagement and consistent patronage — the clearest signal of a well-established, trusted establishment.

### 7. Neighbourhood Reputation is the Second Strongest Driver
A restaurant's locality average rating significantly influences its own rating perception. Restaurants situated in high-quality culinary areas benefit from a "halo effect" — customers associate location prestige with individual restaurant quality.

### 8. Cuisine Type Carries Moderate Predictive Weight
The type of cuisine offered holds meaningful importance, indicating that certain culinary categories carry stronger consumer appeal or loyalty. Multi-cuisine and North Indian restaurants lead in popularity within the dataset.

---

## 🚀 Strategic Recommendations

### For Restaurant Operators
- **Invest in Community Engagement First** — Before premium décor or influencer marketing, focus on accumulating genuine customer reviews. The data confirms votes are the single most powerful rating driver.
- **Leverage Location Intelligence** — If entering a new market, prioritize opening in localities with above-average rating profiles. The neighbourhood effect is real and statistically significant.
- **Offer Online Delivery as a Standard** — Given the positive rating correlation, restaurants without delivery services risk a competitive disadvantage in rating perception, particularly in urban markets.

### For Restaurant Aggregator Platforms (e.g., Zomato, Swiggy)
- **Surface Neighbourhood Ratings** — Build locality-level reputation scores into the UI to help consumers make better-informed choices and to incentivize area-level quality improvement.
- **Design Vote-Incentive Systems Carefully** — Since votes are the top predictor, platform integrity depends on ensuring vote authenticity. Fraudulent engagement manipulation could distort the model's reliability.
- **Flag Low-Engagement New Entrants** — New restaurants with few votes are difficult to rate accurately. A separate quality signal or confidence interval disclosure would improve transparency.

### For Investors & Market Analysts
- **Use Locality Average Rating as a Market Entry Signal** — Areas with consistently high locality ratings represent established food culture and likely higher consumer spending power.
- **Treat Vote Volume as a Proxy for Foot Traffic** — In the absence of actual footfall data, vote counts serve as a reasonable leading indicator for restaurant viability and customer retention.

---

## ✅ Conclusion

*The Palate Predictor* demonstrates that restaurant ratings — often perceived as subjective and unpredictable — are, in fact, significantly explained by quantifiable operational and contextual variables.

Through rigorous data cleaning, creative feature engineering, and ensemble machine learning, this project achieved a highly accurate predictive model (R² = 0.964) that surfaces a clear, data-backed finding: **community engagement and neighbourhood prestige are the twin pillars of a top-rated restaurant.**

For operators, platforms, and investors, this translates into a practical framework — prioritize customer interaction, choose location deliberately, and offer convenience-oriented services as baseline standards.

This project is part of an ongoing portfolio of data analytics and machine learning work in the operations and business intelligence domain.

---

## 📁 Project Structure

```
palate-predictor/
│
├── Restaurant.ipynb          # Main analysis notebook (end-to-end workflow)
├── Restaurant.csv                   # Source dataset (Zomato restaurant data)
├── Restaurant_cleaned.xlsx       # Cleaned and feature-engineered output dataset
└── README.md                 # Project documentation
```

---

## 👤 Author

**Aminu**
Operations Analyst | Data Analytics Professional
📍 Nigeria

[![LinkedIn]www.linkedin.com/in/aminu-abiola-81b64910b

---

*If you found this project insightful, consider giving it a ⭐ on GitHub.*
