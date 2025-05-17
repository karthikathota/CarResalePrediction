# Car Resale Value Predictor

A Python-based tool for predicting car resale values based on various factors including mileage, age, condition, make, and model.

## Features

- Predicts car resale values using a combination of factors:
  - Mileage-based depreciation
  - Age-based depreciation
  - Condition assessment
  - Make and model adjustments
- Provides confidence intervals for predictions
- Supports natural language condition descriptions
- Case-insensitive make and model matching
- Input validation and error handling

## Depreciation Rules

### Mileage Impact

- Below 5,000 miles: Resale value ≈ original price
- 5,000 - 50,000 miles: Decreases by 10% per 10,000 miles
- Above 50,000 miles: Resale value ≈ 40% of original price

### Age Impact

- 5+ years: Base value = 40% of original price
  - Decreases by 5.5% for each additional year
- Less than 5 years: Increases by 10% for each year younger than 5
- Minimum value: 10% of original price

### Condition Impact

- Excellent: 75-80% of original price
- Good: 65-75% of original price
- Fair: 50-60% of original price
- Poor: Less than 50% of original price

### Make and Model Adjustments

- Luxury models: +5% adjustment
- Economy models: -2% adjustment
- Luxury brands: +3% adjustment
- Economy brands: -1% adjustment

## Input Parameters

- `make`: Car manufacturer (e.g., "toyota", "bmw")
- `model_name`: Car model (e.g., "rav4", "x5")
- `year`: Manufacturing year (2000-2024)
- `age`: Car age in years
- `mileage`: Total mileage
- `condition`: Car condition (supports various descriptions)
- `original_price`: Original purchase price ($30,000-$200,000)

## Condition Descriptions

The tool supports various natural language descriptions for car conditions:

### Excellent

- "excellent"
- "like new"
- "mint"
- "perfect"
- "pristine"
- "showroom"
- "brand new"

### Good

- "good"
- "very good"
- "well maintained"
- "clean"
- "nice"
- "decent"

### Fair

- "fair"
- "average"
- "okay"
- "normal"
- "used"
- "typical"

### Poor

- "poor"
- "bad"
- "rough"
- "damaged"
- "needs work"
- "worn"

## Output

The prediction function returns a dictionary containing:

- `estimated_value`: The predicted resale value
- `confidence_interval`: Range of possible values
- `factors`: Impact of each factor on the prediction
- `condition_details`: Standardized condition and its impact

## Requirements

- Python 3.x
- pandas
- numpy
- scikit-learn

## Installation

1. Clone the repository
2. Install required packages:

```bash
pip install pandas numpy scikit-learn
```
