# Fitness Subscription Analytics

Advanced Business Analytics project analyzing customer retention, revenue forecast, and customer acquisition cost (CAC) vs Lifetime Value (LTV) for a fitness subscription business.

## 📊 Key Findings

### 1. Customer Cohort Analysis: When do customers cancel?
- *Highest churn in first 3 months*: Retention drops from 100% to ~55-60% by Month 3.
- Customers typically cancel after *3-4 months* on average.
- After Month 6, retention stabilizes at ~35-40% - these are loyal customers.
- *Insight*: First 3 months are critical - need onboarding and engagement to reduce early churn.

### 2. Revenue Forecast: Next 12 months
- *Forecast Trend*: Subscription revenue shows a steady upward trend over next 12 months.
- *Expected Revenue*: Cumulative forecast indicates continued growth, projected to reach ~2.5M-2.6M monthly by end of forecast (based on historical seasonality).
- *Seasonality: Yes, clear **12-month seasonality* detected. Revenue peaks at beginning of year (Jan-Feb - New Year fitness resolutions) and dips in summer months. Forecast model used Seasonality = 12 points with 95% confidence interval.
- Filter applied: StartOfMonth is not blank to remove null forecast errors.

### 3. CAC vs. LTV: Payback period
- *Overall Break-even: Cumulative LTV crosses CAC line at **Month 4-5*. Customers become profitable after ~5 months.
- *2024 Cohort: Recovers CAC in *~5 months**
- *2025 Cohort: Recovers CAC in *~4 months** (slightly faster payback - better quality or pricing)
- *Current LTV*: ~2.6M cumulative after 20 months vs CAC ~1.7M flat line.
- *Insight*: CAC is recovered quickly. LTV/CAC ratio > 1.5 after Month 10, indicating healthy unit economics. Focus on retaining customers beyond Month 5 to maximize profit.

## 📁 Repository Structure
fitness-subscription-analytics/
├── README.md
├── report.pbix
├── data/
│   └── Fitness_Subscriptions_Dataset.xlsx
└── screenshots/
    ├── cohort_analysis.png
    ├── revenue_forecast.png
    ├── cac_vs_ltv.png
    └── data_model.png

## Tools Used
- Power BI (Forecasting, DAX: Total CAC, Cumulative LTV, Cohort Year)
- DAX Measures: Total CAC = SUM(customers[CAC]), Average CAC, Cumulative LTV = CALCULATE(SUM(transactions[Revenue]), FILTER(ALL(Months Since Start)))

## Recommendation
Focus on Month 0-3 retention programs to push more customers to break-even point (Month 5). 2025 cohorts performing better - replicate their acquisition channel.
