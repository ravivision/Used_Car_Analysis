# Used Car Price Analysis - Executive Summary Report

## Business Objective
Identify key factors that drive used car prices to help a used car dealership optimize inventory and maximize revenue.

---

## Dataset Overview
- **Original Size**: 426,880 records with 18 features
- **Final Dataset**: 31,869 records (after cleaning)
- **Time Period**: Vehicles from 1990-2022
- **Target Variable**: Used car price

---

## Key Findings

### 1. Data Quality Issues
The dataset required significant cleaning:
- **Missing Values**: 30-70% missing in several columns (size, condition, VIN, drive)
- **Unrealistic Values**: Zero prices (2,372 records) and zero odometer readings (81 records)
- **Solution**: Removed records with price < $5,000 and odometer < 5,000 miles, filtered to vehicles after 1990

### 2. Top 5 Price-Driving Features (In Order of Importance)

#### **#1: Diesel Fuel** 
- Strongest positive correlation with price
- Diesel vehicles command significantly higher prices
- **Price Impact**: +$16,538 premium for diesel fuel

#### **#2: Year of Manufacture**
- Newer vehicles have higher prices (positive correlation)
- **Coefficient**: +$10.54 per year
- Strong predictor of value retention

#### **#3: Odometer Reading**
- Negative correlation with price (as expected)
- **Coefficient**: -$0.07 per mile
- Lower mileage = higher price

#### **#4: Four-Wheel Drive (4WD)**
- Positive correlation with price
- **Price Impact**: +$5,881 premium for 4WD

#### **#5: Full-Size Vehicles**
- Larger vehicles command higher prices
- **Price Impact**: +$5,508 premium for full-size

---

## Model Performance

### Recommended Model: Model 7
**Features Used**: Odometer, Year, Fuel (Diesel), Drive (4WD), Size (Full-size)  
**Dataset**: Vehicles > 1990, Price > $5,000, Odometer > 5,000 miles

**Performance Metrics**:
- **Training Accuracy**: 47.52%
- **Test Accuracy**: 48.26%
- **RMSE**: $8,970

### Sample Price Predictions

| Vehicle Description | Predicted Price |
|---------------------|----------------|
| 2020 car, 10k miles, diesel, 4WD, full-size | $48,238 |
| 2020 car, 10k miles, gas, 4WD, full-size | $31,700 |
| 1990 car, 100k miles, diesel, 4WD, full-size | $39,107 |
| 1990 car, 100k miles, gas, 4WD, full-size | $22,570 |

---

## Actionable Recommendations

### For Inventory Management:
1. **Prioritize Diesel Vehicles**: Stock more diesel-powered vehicles as they command the highest price premium
2. **Focus on Newer Models**: Vehicles from 2010+ show better price stability
3. **Target 4WD Vehicles**: All-wheel/four-wheel drive vehicles are valued higher by consumers
4. **Stock Full-Size Vehicles**: Larger vehicles have stronger pricing power

### For Sales Strategy:
1. **Highlight Fuel Type**: Emphasize diesel engines as a premium feature
2. **Low Mileage Matters**: Focus marketing on vehicles with odometer < 100,000 miles
3. **Year and Condition**: Newer vehicles (< 10 years old) with lower mileage are easiest to price and sell

### For Pricing Strategy:
- Use the model coefficients to estimate fair market value
- Adjust pricing based on:
  - Year: +$10.54 per year newer
  - Diesel fuel: +$16,538 premium
  - 4WD: +$5,881 premium
  - Full-size: +$5,508 premium
  - Odometer: -$0.07 per mile

---

## Model Limitations & Next Steps

### Current Limitations:
- **Moderate Accuracy** (48%): Indicates other factors influence pricing
- **Data Quality**: Original dataset had significant missing/unrealistic values
- **Limited Features**: Excluded manufacturer, model, color, and other potentially relevant factors

### Recommendations for Improvement:
1. **Collect Better Data**: Include modern features (safety tech, infotainment, cameras, adaptive cruise control)
2. **Focus on Recent Vehicles**: Build separate model for cars 2010+ for higher accuracy
3. **Add Features**: Include manufacturer, specific models, and regional factors
4. **Increase Dataset**: Gather more recent sales data (2020-2023) for better predictions
5. **Target Accuracy**: Aim for 75%+ accuracy with improved data quality

---

## Conclusion

The analysis successfully identified **five key drivers** of used car prices:
1. **Diesel Fuel** (most important)
2. **Year of Manufacture**
3. **Odometer Reading**
4. **Four-Wheel Drive**
5. **Full-Size Vehicles**

**Bottom Line**: To maximize profitability, the dealership should prioritize stocking newer diesel-powered, 4WD, full-size vehicles with lower mileage. These vehicles command the highest prices and represent what consumers value most in the used car market.

The current model provides a solid foundation for pricing decisions but should be enhanced with better quality data and additional features for production deployment.

---
