# Walmart Sales Prediction

![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📊 Project Overview

This machine learning project focuses on predicting weekly sales for Walmart stores using historical sales data and various external factors. The project implements multiple regression models to forecast sales and help optimize inventory management and business planning.

## 🎯 Key Features

### Data Analysis & Preprocessing
- Comprehensive exploratory data analysis
- Advanced feature engineering
- Data cleaning and preprocessing pipeline
- Handling of missing values and outliers

### Machine Learning Models
- Linear Regression
- Ridge Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- Decision Trees
- XGBoost

### Visualization & Analysis
- Interactive data visualizations using Plotly
- Statistical analysis with Seaborn
- Performance metrics visualization
- Model comparison charts

## 🛠️ Technical Requirements

### System Requirements
- Python 3.x
- 8GB RAM minimum (16GB recommended)
- 1GB free disk space

### Python Dependencies
```python
numpy>=1.20.0
pandas>=1.3.0
scikit-learn>=0.24.0
xgboost>=1.5.0
category_encoders>=2.6.0
plotly>=5.3.0
seaborn>=0.11.0
matplotlib>=3.4.0
```

## 🚀 Installation Guide

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/walmart-sales-prediction.git
   cd walmart-sales-prediction
   ```

2. **Set Up Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## 📖 Usage Guide

1. Open the Jupyter notebook `Walmart_sales_prediction.ipynb`
2. Run the cells sequentially to:
   - Load and preprocess the data
   - Perform exploratory data analysis
   - Train and evaluate models
   - Generate predictions

## 📊 Dataset Features

The dataset includes the following features:
- Store: Store identifier
- Date: Week of sales
- Weekly_Sales: Sales for the given store
- Holiday_Flag: Whether the week is a special holiday week
- Temperature: Average temperature in the region
- Fuel_Price: Cost of fuel in the region
- CPI: Consumer Price Index
- Unemployment: Unemployment rate

## 📊 Exploratory Data Analysis (EDA)

### Statistical Analysis

#### Temperature Analysis
- Mean: 60.66°F
- Median: 62.67°F
- Mode: 50.43°F
- Skewness: -0.34
- Impact: Lower mode temperature indicates increased winter product sales

#### Fuel Price Analysis
- Mean: $3.36/gallon
- Median: $3.45/gallon
- Mode: $3.64/gallon
- Skewness: -0.10
- Impact: Higher mode price suggests consumer adaptability to price changes

#### CPI (Consumer Price Index) Analysis
- Mean: 171.58
- Median: 182.62
- Mode: 126.06
- Skewness: 0.06
- Impact: Higher CPI indicates reduced consumer purchasing power

#### Unemployment Analysis
- Mean: 8.00%
- Median: 7.87%
- Mode: 8.10%
- Skewness: 1.19
- Impact: Higher unemployment correlates with decreased consumer spending

### Time Series Analysis
- **Sales Patterns**:
  - Recurring spikes in late 2010, 2011, and 2012
  - Highest peak: >$2,000,000 (year-end holiday season)
  - Regular fluctuations: $800,000 - $1,200,000 (non-peak periods)
  - Strong seasonal trends with consistent annual peaks

### Box Plot Analysis

#### Temperature Distribution
- Median: ~70°F
- Wide interquartile range (IQR)
- Outliers present on both lower and higher ends
- Indicates significant temperature variability

#### Fuel Price Distribution
- Median: Slightly above $3.50
- Narrower IQR compared to temperature
- Few outliers on higher end
- Less price variability

#### CPI Distribution
- Median: ~215
- Small IQR
- No outliers
- Consistent CPI values

#### Unemployment Distribution
- Median: Just below 8%
- Symmetric IQR spread
- Several upper-end outliers
- Indicates periods of significantly higher unemployment

### Correlation Analysis

#### Weekly Sales Correlations
- Temperature: -0.064 (very weak negative)
- Fuel Price: 0.0095 (negligible)
- CPI: -0.073 (very weak negative)
- Unemployment: -0.11 (weak negative)
- Holiday Flag: 0.037 (very weak positive)
- Month: 0.076 (weak positive)
- Year: No direct correlation (indicates underlying trends)

### Key Insights
1. **Seasonal Impact**
   - Strong seasonal patterns in sales
   - Holiday periods show significant influence
   - Year-end season shows highest sales

2. **Economic Factors**
   - Unemployment has the strongest correlation with sales
   - CPI and temperature show minimal direct impact
   - Fuel prices have negligible effect on sales

3. **Data Distribution**
   - Temperature shows highest variability
   - CPI remains relatively stable
   - Unemployment shows occasional spikes

## 🔬 Techniques Used

### Data Preprocessing
1. **Data Quality Checks**
   - Verified absence of missing values
   - Confirmed no duplicate records
   - Ensured data integrity

2. **Data Type Adjustments**
   - Converted Date column to datetime format
   - Standardized data types for analysis

3. **Outlier Detection and Handling**
   - Identified outliers in Weekly_Sales, Temperature, and Unemployment
   - Applied 1.5 * IQR rule for outlier treatment
   - Retained 91.95% of original dataset

4. **Feature Engineering**
   - Extracted Year, Month, and Week from Date
   - Captured temporal patterns and seasonal effects
   - Dropped redundant Date column

5. **Data Transformation**
   - Standardized numerical features (Weekly_Sales, Temperature, Fuel_Price, CPI, Unemployment)
   - Applied StandardScaler for zero mean and unit variance
   - One-hot encoded Store and Season columns

6. **Data Splitting**
   - 80-20 train-test split
   - Training set: 4,733 samples
   - Testing set: 1,184 samples

### Model Implementation
1. **Linear Models**
   - Linear Regression with regularization
   - Ridge Regression with cross-validation
   - Feature scaling and normalization

2. **Tree-Based Models**
   - Random Forest with hyperparameter tuning
   - Decision Trees with pruning
   - XGBoost with early stopping

3. **K-Nearest Neighbors**
   - Distance metric optimization
   - K-value selection
   - Feature scaling

### Model Evaluation
1. **Metrics Used**
   - Mean Absolute Error (MAE)
   - Mean Squared Error (MSE)
   - Root Mean Squared Error (RMSE)
   - R-squared Score
   - Cross-validation scores

2. **Validation Techniques**
   - K-fold cross-validation
   - Train-test split
   - Time series validation

## 📈 Results

### Model Performance Comparison
| Model | MAE | MSE | RMSE | R² Score | CV Score |
|-------|-----|-----|------|----------|-----------|
| Linear Regression (Before) | 0.737 | 0.772 | 0.879 | 0.237 | ~0.1 |
| Linear Regression (After) | 0.122 | 0.041 | 0.201 | 0.959 | ~0.9 |
| KNN (Before) | 0.243 | 0.159 | 0.398 | 0.840 | ~0.85 |
| KNN (After) | 0.149 | 0.083 | 0.288 | 0.916 | ~0.9 |
| Decision Tree (Before) | 0.145 | 0.070 | 0.264 | 0.930 | ~0.9 |
| Decision Tree (After) | 0.141 | 0.065 | 0.255 | 0.934 | ~0.95 |
| Random Forest (Before) | 0.117 | 0.043 | 0.207 | 0.957 | ~0.95 |
| Random Forest (After) | 0.118 | 0.044 | 0.209 | 0.956 | ~0.95 |
| XGBoost (Before) | 0.113 | 0.033 | 0.182 | 0.967 | ~0.95 |
| XGBoost (After) | 0.104 | 0.032 | 0.178 | 0.968 | ~0.95 |

### Key Findings
1. **Model Performance**
   - XGBoost emerged as the best performing model with highest R² score (0.968)
   - Linear Regression showed most dramatic improvement after tuning
   - Random Forest and XGBoost maintained consistent high performance

2. **Hyperparameter Tuning Impact**
   - Linear Regression: Most significant improvement (R²: 0.237 → 0.959)
   - KNN: Complex case with improved R² but increased error metrics
   - Decision Tree: Marginal improvements
   - Random Forest: Negligible changes
   - XGBoost: Slight but consistent improvements

3. **Cross-Validation Insights**
   - Linear Regression: Greatest improvement (~0.1 → ~0.9)
   - KNN: Moderate improvement (~0.85 → ~0.9)
   - Decision Tree: Small increase (~0.9 → ~0.95)
   - Random Forest: Consistent high performance (~0.95)
   - XGBoost: Minimal but positive change (~0.95)

### Business Impact
1. **Sales Forecasting**
   - High accuracy in predicting weekly sales
   - Improved inventory management potential
   - Enhanced holiday season planning

2. **Model Reliability**
   - XGBoost provides most reliable predictions
   - Consistent performance across different data subsets
   - Robust to variations in the dataset

### Visualization Results
1. **Sales Patterns**
   - Weekly sales trends
   - Holiday impact analysis
   - Store performance comparison

2. **Feature Relationships**
   - Correlation heatmaps
   - Feature importance plots
   - Residual analysis

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Author

- **Praharsh Vijay Medi** - *Implementation* - [GitHub Profile](https://github.com/dimpupraharsh)

## 📞 Support

For questions or issues:
1. Check the [Issues](https://github.com/dimpupraharsh/walmart-sales-prediction/issues) section
2. Create a new issue if your problem isn't already listed
3. Contact: praharsh789@gmail.com

## 🔄 Future Improvements

- [ ] Add more advanced feature engineering techniques
- [ ] Implement deep learning models
- [ ] Add automated hyperparameter optimization
- [ ] Create a web interface for predictions
- [ ] Add support for real-time predictions
- [ ] Implement model explainability tools

## 📚 Resources

- Scikit-learn Documentation
- XGBoost Documentation
- Pandas Documentation
- Plotly Documentation

---

⭐ Star this repository if you find it useful! 
