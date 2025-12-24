# Trader Behavior vs Market Sentiment Analysis

## Objective
This project explores the relationship between **trader performance** and **Bitcoin market sentiment** to uncover behavioral patterns that can drive smarter trading strategies.  
The analysis focuses on understanding how different sentiment regimes impact trader profitability and behavior.

---

## Datasets Used

### 1️ Bitcoin Fear & Greed Index
- **Columns**: `date`, `value`, `classification`
- **Description**:
  - `value` (0–100): Numerical sentiment strength
  - `classification`: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

### 2️ Hyperliquid Historical Trader Data
- **Key Columns**:
  - `account`, `symbol`, `side`
  - `execution price`, `size`, `leverage`
  - `Closed PnL`, `time`

---

##  Tools & Technologies
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook
- VS Code

---

##  Methodology

1. **Data Cleaning & Preprocessing**
   - Converted timestamps to daily dates
   - Merged trader data with daily market sentiment
   - Handled breakeven (PnL = 0) trades separately

2. **Sentiment Encoding**
   - Used:
     - Categorical sentiment (`classification`)
     - Numerical sentiment strength (`value`)
     - Bucketed sentiment regimes

3. **Performance Metrics**
   - Average PnL
   - Win rate
   - Trade frequency

4. **Trader Segmentation**
   - Traders classified as:
     - **Consistently Profitable**
     - **Consistently Losing**
   - Based on cumulative Closed PnL

---

## Key Findings

###  1. Sentiment Alone Does Not Predict Profitability
- Overall correlation between sentiment value and PnL is near zero
- Indicates **non-linear and regime-dependent behavior**

###  2. Extreme Sentiment Regimes Matter
- **Extreme Greed**:
  - Highest average PnL
  - Best win rates (momentum-driven)
- **Extreme Fear**:
  - Lower win rates
  - High asymmetric payoff opportunities (mean reversion)

###  3. Profitable vs Losing Trader Behavior
- Profitable traders:
  - Trade less frequently
  - Achieve very high win rates during Extreme Fear
  - Avoid low-conviction (neutral) markets
- Losing traders:
  - Overtrade across all sentiment regimes
  - Fail to adapt strategy to market conditions

> **Key Insight:**  
> *Market sentiment does not drive profitability — trader behavior under sentiment does.*

---

##  Strategy Implications

- Momentum strategies perform best during **Extreme Greed**
- Selective mean-reversion strategies succeed during **Extreme Fear**
- Overtrading in emotional markets leads to persistent losses
- Sentiment-aware risk controls can significantly improve outcomes

---

---

## Conclusion
This analysis demonstrates that **behavioral discipline, selectivity, and regime awareness** are the primary drivers of consistent trading performance.  
The findings provide actionable insights for traders, analysts, and trading platforms aiming to improve decision-making in volatile crypto markets.
