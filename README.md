# Project Summary: Market Sentiment & Trader Performance Analysis

## 1. Methodology
This analysis integrated historical Hyperliquid trader transaction data with the Bitcoin Fear & Greed Index to understand how market psychology influences performance. 

*   **Data Preparation**: Cleaned and aligned 180k+ transaction records with daily sentiment states. Fixed timestamp discrepancies to ensure accurate daily performance attribution.
*   **Feature Engineering**: Developed advanced metrics including **Sentiment Volatility** (7-day rolling std dev of the index) and **Rolling Win Rates** (7-day account-level trends).
*   **Behavioral Clustering**: Applied K-Means clustering to identify archetypes such as 'Fear-Driven Opportunists,' 'High-Intensity Whales,' and 'Retail' segments.
*   **Predictive Modeling**: Developed a Random Forest Classifier to predict next-day profitability. Addressed class imbalance using **SMOTE** and optimized hyperparameters via Randomized Search (achieving a 0.74 ROC-AUC).
*   **Interactive Exploration**: Built an IPython dashboard to filter and visualize performance metrics by segment.

## 2. Key Insights
*   **Fear is Profitable**: Traders achieved their highest mean daily PnL (~$209k) and win rates (41.6%) during 'Fear' states. Market participants significantly increased trading frequency (4,183 avg trades/day) during these periods.
*   **Sentiment Volatility as a Signal**: The predictive model identified sentiment volatility as a critical feature. Rapid shifts in market mood are stronger predictors of shifting profitability than the absolute sentiment value itself.
*   **Segment Divergence**: 'Whales' demonstrated higher resilience and profitability during extreme market fear, while 'Retail' segments saw their best relative performance during stable 'Greed' periods.
*   **Neutral Trap**: 'Neutral' sentiment correlated with the lowest win rates (26.1%) and frequent PnL erosion, suggesting 'choppy' markets are the most difficult to navigate.

## 3. Strategy Recommendations
*   **The Contrarian Rule**: Increase trading frequency and maintain exposure when the Fear & Greed Index drops. Historically, 'Fear' windows represent the most efficient periods for high-frequency strategies to capture PnL.
*   **Volatility-Based De-risking**: When 7-day sentiment volatility spikes (regardless of the index direction), traders should reduce position sizes or tighten stop-losses, as the model shows these conditions correlate with a drop in predictable profitability.
*   **Avoid the 'Choppy Middle'**: Reduce activity when the Index is in the 'Neutral' zone (40-60). Focus capital on high-sentiment conviction periods where win rates are statistically superior.

  ## Summary:


### Data Analysis Key Findings

*   **Model Accuracy and Reliability**: The optimized Random Forest model achieved an overall accuracy of **69%**. It maintained a high recall of **0.82** for profitable days, ensuring most opportunities are captured, while improving precision for non-profitable days to **0.50**.
*   **Predictive Power**: The **ROC-AUC score of 0.7364** indicates that the combination of sentiment volatility and rolling win rates provides a solid diagnostic capability to differentiate market outcomes beyond random chance.
*   **Optimized Parameters**: The best-performing model utilized **300 estimators** with no maximum depth and no bootstrapping, which maximized the F1-score during cross-validation.
*   **Segmented Behavior**: Interactive visualizations revealed distinct behaviors across segments; for instance, high-frequency segments showed varying win-rate stability depending on whether the market was in a state of "Fear" or "Greed."

## To Run the .ipynb File -
   Simply Upload both the csv files and Run the code.
