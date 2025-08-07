# 📈 Forecasting Yearly Trends with Linear Regression in R

## 🔍 Project Overview

This project demonstrates how to model and forecast **year-over-year trends** using simple linear regression on time series data. The example is based on a fictional dataset tracking purchases over a five-year period (2020–2024), but the approach is broadly applicable to many industries.

### Applicable Use Cases:
- 📚 **Education** – Forecasting student applications
- 🛍️ **Retail** – Predicting annual sales or purchases
- 💼 **HR** – Projecting yearly hires or attrition
- 🏥 **Healthcare** – Estimating patient visits or claims
- 📈 **Finance** – Anticipating new account openings or investments

---

## 📊 Dataset

**File:** `yearly_activity_data.csv`  
**Structure:**
- `Year`: Integer (e.g., 2020, 2021, ...)
- `Purchases`: Numeric value representing quantity of interest

> 📝 *Note: This dataset is fictional and created for demonstration purposes only.*

---

## 📦 R Packages Used

```r
library(ggplot2)
```

---

## 🔨 Workflow Summary

```r
# Set working directory
setwd("your_working_directory")

# Load dataset
XYZdf <- read.csv("yearly_activity_data.csv")

# Plot the time series
ggplot(data = XYZdf, aes(x = Year, y = Purchases)) +
  geom_line() +
  geom_point() +
  labs(title = "Purchases by Year (2020–2024)",
       x = "Year",
       y = "Purchases")

# Add a numeric time variable
XYZdf$Time <- 1:nrow(XYZdf)

# Fit a linear regression model
model <- lm(Purchases ~ Time, data = XYZdf)
summary(model)

# Forecast purchases for 2025 (Time = 6)
new_time <- data.frame(Time = 6)
predict(model, newdata = new_time)
```

---

## 💡 Insights & Takeaways

- Linear regression provides a **transparent, interpretable model** for identifying trends.
- Useful in early-stage forecasting or when a **quick baseline prediction** is needed.
- Can support **budgeting, planning, and strategy** across industries.

---

## 📁 Files Included

- `yearly_activity_data.csv` – Synthetic dataset
- `trend_forecasting.R` – Analysis script
- `README.md` – Project documentation

