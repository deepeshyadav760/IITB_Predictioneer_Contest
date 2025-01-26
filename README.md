# Comprehensive Analysis of Ebola Outbreak Prediction Model

## Introduction and Project Overview
This project analyzes an **Ebola outbreak prediction model** developed using machine learning techniques and epidemiological principles. The model predicts outbreak patterns, death rates, and case fatality ratios (CFR) across geographical locations, aiding public health interventions.

---

## Data Overview & Characteristics

### Dataset Structure
The analysis uses two datasets:
- **Training Dataset:**
  - 3,925 records
  - Geographic coordinates: latitude (-71.95° to 71.71°), longitude (-178.12° to 178.07°)
  - Death records: 2,458 complete entries (1,558 missing)
  - CFR: 3,972 records
- **Test Dataset:**
  - 4,016 locations requiring predictions

### Statistical Distribution
Key metrics from the training data:

| Metric  | Mean  | Std Dev | Min | Max   |
|---------|-------|---------|-----|-------|
| Deaths  | 70.75 | 55.36   | 0   | 200   |
| CFR (%) | 13.90 | 123.02  | 0   | 7570.77 |

---

## Methodological Framework

### Feature Engineering Architecture
- **Geographic Distance Calculation:**
  The model uses the **Haversine formula**:



- \(d\): Great-circle distance
- \(R\): Earth's radius (6371 km)
- \(\phi₁, \phi₂\): Latitudes
- \(\Delta\lambda\): Longitude difference

- **Outbreak Centers Identified:**

| Location      | Latitude  | Longitude  |
|---------------|-----------|------------|
| Liberia       | 6.4281°   | -9.4295°   |
| Sierra Leone  | 8.4606°   | -13.2317°  |
| Guinea        | 9.9456°   | -9.6966°   |

- **Regional Analysis:**
- Implemented **K-means clustering** (k=8) to identify variations.
- Example findings:
  - Region 5: Highest mortality (52.95 ± 60.84 deaths)
  - Region 3: Lowest mortality (5.42 ± 22.76 deaths)

---

## Model Architecture & Implementation

### RandomForest Configuration
Optimized hyperparameters:
- `max_depth`: 6  
- `min_samples_leaf`: 2  
- `min_samples_split`: 6  
- `n_estimators`: 400  

### Performance Metrics
- **R² Score:** 39.06% variance explained
- **Distance Effects:**



---

## Prediction Analysis & Results

### Test Data Predictions
Prediction statistics for key metrics:

| Metric           | Mean   | SD     | Range         |
|-------------------|--------|--------|---------------|
| Deaths           | 84.35  | 23.35  | 50-151.14     |
| CFR (%)          | 25.01  | 0.03   | 25-25.9       |
| Confirmed Cases  | 337.23 | 93.37  | 193.05-604.27 |

---

## Domain Knowledge Integration

### Epidemiological Principles
- **Distance Decay Correlations:**
- Correlations between distance and deaths:
  - \(corr(dist_0, deaths) = -0.071\)  
  - \(corr(dist_1, deaths) = -0.068\)  
  - \(corr(dist_2, deaths) = -0.073\)  

- **Healthcare Capacity Integration:**
- CFR range constraints: 25-90%
- Geographic accessibility considerations
- Regional clustering patterns

---

## Model Limitations & Future Enhancements

### Current Limitations
1. **Performance Constraints:**
 - Moderate R² score (0.3906)
 - Geographic bias in training data
 - Limited temporal feature integration
2. **Data Quality Issues:**
 - Missing death records (1,558)
 - Potential reporting biases
 - Geographic coverage gaps

### Enhancement Strategies
- **Technical Improvements:**
- Advanced feature engineering
- Temporal pattern integration
- **Data Enhancements:**
- Additional data sources (e.g., healthcare infrastructure data)
- Improved geographic coverage

---

## Application to New Locations

### Implementation Framework
1. **Geographic Processing:**
 - Coordinate standardization
 - Distance calculation
 - Regional cluster assignment
2. **Prediction Pipeline:**
 - Death rate prediction
 - CFR calculation
 - Confirmed cases estimation

### Validation Methodology
Quality assurance includes:
- Geographic validation
- Epidemiological consistency checks
- Regional pattern validation

---

## Conclusion
This model combines machine learning with epidemiological principles to predict Ebola outbreak patterns. Despite current limitations, it provides a solid foundation for public health applications. Future work will enhance its data quality and modeling sophistication to improve prediction accuracy and reliability.


## Cloning the Repository

To clone this repository, follow these steps:

1. Open your terminal or command prompt.
2. Use the `git clone` command along with the repository URL.

### Command to Clone

```bash
git clone https://github.com/deepeshyadav760/IITB_Predictioneer_Contest.git
