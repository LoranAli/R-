# R
# CAPM Analysis on Stockholm Stock Exchange Data

**Summary:**  
This project analyzes the Capital Asset Pricing Model (CAPM) using daily stock prices from the Stockholm Stock Exchange. The main goal is to assess whether the relationship between stock returns and beta times market return (OMX30 index) is statistically significant.

## Project Details

- **Data**: Daily stock prices (2015–2018) for various stocks and the OMX30 index as the market benchmark. The risk-free rate was excluded.
- **Objective**:  
  - Estimate beta for selected stocks (measuring sensitivity to market movements)
  - Test the statistical significance of the relationship between beta and stock returns

## Steps and Results

### 1. Data Preparation & Transformation
- Loaded stock and index data, converted prices to daily percentage returns
- Filtered out stocks with missing data and sampled 20 stocks for analysis

### 2. Estimation of Beta
- Ran regressions for each stock to estimate alpha, beta, and residual variance against the market index

### 3. CAPM Second-Stage Regression
- Regressed the average stock returns against estimated betas
- Found:
  - Intercept is statistically significant (suggests baseline returns beyond beta)
  - Slope is not significant at 5% (implies weak beta-return relationship)

### 4. Statistical Testing
- Manual t-tests confirmed:
  - The intercept is significantly different from zero (contradicts CAPM assumption)
  - The slope matches the average index return at the 5% significance level

### 5. Visualization
- Plotted average returns vs. beta coefficients
- Figure shows the estimated relationship with a regression line, illustrating the (lack of) correlation between beta and returns

## Conclusions

- The significant intercept suggests unexplained returns beyond market risk (beta), challenging the CAPM assumption.
- The slope aligns with market returns, partially supporting the CAPM model.
- Overall, results show only weak evidence for a beta-return trade-off in this sample.

---

**How to run:**  
Open `capm_analysis.R` in RStudio. Ensure `SSE_Stocks.xlsx` and `OMX_Stockholm_30.xlsx` are in the same folder.

---

**Files:**
- `capm_analysis.R`: R script for CAPM analysis and visualization.
- `SSE_Stocks.xlsx`: Daily stock price data for analysis.
- `OMX_Stockholm_30.xlsx`: Market index data.
- `report.md`: Project description and results (this file).

---
