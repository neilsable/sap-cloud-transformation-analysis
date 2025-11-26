# 📊 Methodology Documentation

## Data Collection & Extraction

### Primary Data Source
**Document:** SAP SE Q3 2025 Quarterly Statement  
**Published:** October 22, 2025  
**Type:** Official SEC filing / Earnings release  
**Pages:** 26 pages total  
**Verification:** Audited financial data, publicly available  

### Data Extraction Points
| Metric | Source Page | Table/Section |
|--------|-------------|---------------|
| Cloud Revenue (7 quarters) | Pages 8-9 | Financial and Non-Financial Key Facts |
| Cloud Gross Margin | Pages 8-9 | Margins table |
| Operating Profit | Pages 8-9 | Profits section |
| Regional Revenue | Pages 23-24 | Revenue by Region (IFRS and Non-IFRS) |
| Cloud Backlog | Page 2 | Executive summary |
| Predictable Revenue % | Page 2 | Key highlights |

---

## Analytical Methods

### 1. Growth Rate Calculations

**Quarter-over-Quarter (QoQ) Growth:**
```
Formula: (Current Quarter - Previous Quarter) / Previous Quarter
Purpose: Measure sequential momentum
Example: Q3 2025 vs Q2 2025
```

**Year-over-Year (YoY) Growth:**
```
Formula: (Current Quarter - Same Quarter Prior Year) / Same Quarter Prior Year  
Purpose: Remove seasonal effects
Example: Q3 2025 vs Q3 2024
```

**Compound Annual Growth Rate (CAGR):**
```
Formula: (Ending Value / Beginning Value)^(1/years) - 1
Purpose: Normalize growth across periods
Application: Q1 2024 → Q3 2025 (1.75 years)
Result: 18.1% CAGR
```

**Citations:**
- Ross, S., Westerfield, R., & Jaffe, J. (2019). *Corporate Finance*. McGraw-Hill Education.

---

### 2. Linear Regression Forecasting

**Method:** Ordinary Least Squares (OLS)

**Model Equation:**
```
y = mx + b
Where:
- y = Cloud Revenue (€M)
- x = Quarter Number (1, 2, 3, ... 8)
- m = Slope = 195 (€195M per quarter)
- b = Intercept = 3,730
```

**Model Statistics:**
- **R² = 0.96** (96% of variance explained)
- **Standard Error = ±€150M**
- **Sample Size:** 7 quarters (Q1 2024 - Q3 2025)

**Validation:**
- Residual analysis: No autocorrelation detected
- Normality: Residuals approximately normal
- Homoscedasticity: Constant variance confirmed

**Q4 2025 Forecast:**
```
y = 195(8) + 3,730 = 5,290M €

95% Confidence Interval:
Lower: 5,290 - (1.96 × 150) = 4,996M €
Point: 5,290M €
Upper: 5,290 + (1.96 × 150) = 5,584M €
```

**Citations:**
- Kutner, M., Nachtsheim, C., Neter, J., & Li, W. (2004). *Applied Linear Statistical Models* (5th ed.). McGraw-Hill/Irwin.

---

### 3. Statistical Confidence Intervals

**Formula:**
```
CI = Point Estimate ± (Critical Value × Standard Error)

For 95% confidence:
CI = Forecast ± (1.96 × SE)
```

**Interpretation:**
- We are 95% confident the true Q4 2025 cloud revenue falls between €5.0B and €5.6B
- 1.96 is the z-score for 95% confidence in a normal distribution
- If we repeated this analysis 100 times, 95 times the actual value would fall within our interval

**Citations:**
- Anderson, D., Sweeney, D., Williams, T., Camm, J., & Cochran, J. (2020). *Statistics for Business & Economics* (14th ed.). Cengage Learning.

---

### 4. Volatility & Stability Metrics

**Standard Deviation:**
```
σ = √[Σ(xi - μ)² / n]
Result: €510M

Interpretation: Cloud revenue varies by ±€510M quarter-to-quarter
```

**Coefficient of Variation (CV):**
```
CV = (Standard Deviation / Mean) × 100%
Result: 11.2%

Interpretation: 
- CV < 15% = Low volatility (stable)
- CV 15-30% = Moderate volatility
- CV > 30% = High volatility

SAP's 11.2% indicates stable, predictable revenue
```

---

### 5. Market Concentration Analysis

**Herfindahl-Hirschman Index (HHI):**
```
Formula: Σ(market_share²) × 10,000

Calculation for SAP regions:
EMEA: (42.9%)² = 0.184
Americas: (42.5%)² = 0.181
APJ: (14.6%)² = 0.021
Sum: 0.386

HHI = 0.386 × 10,000 = 3,860
```

**Interpretation (DOJ/FTC Guidelines):**
- HHI < 1,500: Competitive market
- HHI 1,500-2,500: Moderate concentration
- **HHI > 2,500: High concentration** ← SAP is here

**Implication:**  
SAP's geographic revenue is highly concentrated in two regions (EMEA + Americas = 85%), creating portfolio risk if either market slows.

**Citations:**
- U.S. Department of Justice & Federal Trade Commission. (2010). *Horizontal Merger Guidelines*.

---

## Assumptions & Limitations

### Assumptions

1. **Data Accuracy**
   - Assumption: SAP's published figures are accurate
   - Justification: Public company (NYSE: SAP), audited financials
   - Risk Level: Low

2. **Linear Growth Pattern**
   - Assumption: Cloud revenue growth follows linear trend
   - Justification: R² = 0.96 validates linear fit for 7-quarter period
   - Limitation: May not capture Q4 seasonality
   - Risk Level: Medium

3. **Currency Stability**
   - Assumption: Analysis uses "actual currency" reported figures
   - Note: SAP also reports "constant currency" adjustments
   - Justification: Actual currency is more conservative
   - Impact: Forecast may understate if USD strengthens

4. **No Structural Changes**
   - Assumption: No major M&A or business model shifts in forecast period
   - Note: SmartRecruiters acquisition (€751M, Sept 2025) deemed immaterial per SAP
   - Risk Level: Low for Q4 2025

### Limitations

1. **Time Series Length**
   - Available: 7 quarters (21 months)
   - Ideal: 12+ quarters for seasonal analysis
   - Impact: Cannot assess multi-year cyclical patterns
   - Mitigation: Model validated with strong R², will update as more data available

2. **Product-Level Detail**
   - Not Disclosed: BTP, S/4HANA, SuccessFactors individual revenue
   - Available: Aggregate "Cloud ERP Suite" only
   - Impact: Cannot isolate BTP contribution
   - Mitigation: Analyzed at disclosed aggregation level

3. **Customer Metrics**
   - Not Disclosed: Retention rates, cohort behavior, customer counts
   - Available: Deal size ranges (>€5M, €1-5M, <€1M as % of order volume)
   - Impact: Cannot perform detailed cohort analysis
   - Mitigation: Used available order entry data for pattern identification

4. **Competitive Benchmarking**
   - Not Included: Oracle, Microsoft, Salesforce comparisons
   - Reason: Different revenue categorizations require normalization and estimation
   - Decision: Maintained "zero estimation" principle over completeness
   - Future: Could add if normalized public data becomes available

---

## Quality Assurance

### Data Validation
✅ All source data manually verified against original document  
✅ Each data point includes page number reference  
✅ No hardcoded values in formulas (except documented constants)  
✅ All formulas auditable and transparent  

### Statistical Validation
✅ Residual analysis performed (no autocorrelation)  
✅ Model fit assessed (R² = 0.96 excellent)  
✅ Confidence intervals calculated using standard methods  
✅ Sensitivity analysis performed  

### Documentation
✅ Complete methodology documented  
✅ All citations included  
✅ Assumptions explicitly stated  
✅ Limitations acknowledged  

---

## Software & Tools

**Microsoft Excel:**
- Version: Excel for Mac/Windows 2016+
- Functions Used: SLOPE, INTERCEPT, RSQ, STDEV.S, AVERAGE, SUM
- Features: Tables, Charts, Conditional Formatting
- No Macros: All analysis uses native Excel functions

**No External Tools:**
- No Python/R used (to demonstrate Excel proficiency)
- No database queries (data extracted manually)
- No third-party add-ins required

---

## Reproducibility

This analysis is fully reproducible:

1. **Source Document:** Publicly available at sap.com/investor
2. **Data Extraction:** Page numbers provided for all data points
3. **Formulas:** All visible in Excel workbook
4. **Calculations:** Step-by-step in this document

**To reproduce:**
1. Download SAP Q3 2025 Quarterly Statement
2. Extract data from pages 2, 5, 8-9, 23-24
3. Apply formulas documented here
4. Results should match within rounding

---

## Version History

**Version 1.0** (November 2025)
- Initial analysis
- Data through Q3 2025
- Q4 2025 forecast

**Planned Updates:**
- Version 1.1 (January 2026): Add Q4 actuals, calculate forecast accuracy
- Version 2.0 (Q1 2026): Full year 2025 retrospective

---

**Last Updated:** November 2025  
**Author:** Neil Sable  
**License:** MIT
