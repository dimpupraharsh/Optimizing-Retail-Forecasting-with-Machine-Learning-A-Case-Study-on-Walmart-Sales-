# Greenhouse Gas Emissions Analysis Project

![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📊 Project Overview

This project provides a comprehensive analysis and visualization toolkit for greenhouse gas emissions data across different countries from 1990 to 2020. It offers powerful data processing capabilities and multiple visualization options to help understand global emission patterns and trends.

## 🎯 Key Features

### Data Processing
- Automated data cleaning and preprocessing pipeline
- Intelligent handling of missing values and data type conversions
- Efficient calculation of total emissions across multiple years
- Smart identification of top emitting countries

### Visualization Capabilities
- **Pie Charts**: Distribution analysis of emissions among top countries
- **Line Charts**: Temporal trend analysis from 1990 to 2020
- **Bar Charts**: Comparative analysis of emissions across countries

## 🛠️ Technical Requirements

### System Requirements
- Python 3.x or higher
- 4GB RAM minimum (8GB recommended)
- 500MB free disk space

### Python Dependencies
```python
pandas>=1.3.0
matplotlib>=3.4.0
```

## 🚀 Installation Guide

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/greenhouse-emissions-analysis.git
   cd greenhouse-emissions-analysis
   ```

2. **Set Up Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## 📖 Usage Guide

### Data Processing Functions

#### 1. Reading Data
```python
from Assignment1 import read_csv
data = read_csv('path_to_your_data.csv')
```

#### 2. Data Cleaning
```python
cleaned_data = clean_data(
    source_data=data,
    data_cols=["1990", "2000", "2013", "2014", "2015", "2016", "2017", "2018", "2019", "2020"],
    drop_col='Series Name'
)
```

#### 3. Total Emissions Calculation
```python
total_emissions = total_emission_data(cleaned_data, columns_to_clean)
```

### Visualization Functions

#### 1. Pie Chart
```python
pie_chart(
    plot_data=top_emission_df,
    data_point_col='total_emissions',
    item_col='Country Name',
    title="Countries with Highest Greenhouse Gas Emissions (1990-2020)"
)
```

#### 2. Line Chart
```python
line_chart(
    plot_data=line_plot_data,
    x_label='Year',
    y_label='Million Metric tons of CO2 Equivalent',
    title='Global Greenhouse Emission Trends (1990-2020)'
)
```

#### 3. Bar Chart
```python
bar_chart(
    dataframe=top_emission_df,
    item='Country Name',
    data_col='2000',
    x_label='Countries',
    y_label='Million Metric tons of CO2 Equivalent',
    title='Greenhouse Emissions by Country (2000)'
)
```

## 📊 Data Structure

The project works with CSV data containing the following columns:
- Country Name
- Series Name
- Year columns (1990-2020)
- Calculated total emissions

## 📈 Output Examples

The script generates three types of visualizations:

1. **Pie Chart**: Shows the proportional distribution of emissions among top emitting countries
2. **Line Chart**: Displays the emission trends over time (1990-2020)
3. **Bar Chart**: Compares emissions of top countries for a specific year (2000)

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contribution Guidelines
- Follow PEP 8 style guide
- Add comments for complex logic
- Update documentation for new features
- Write unit tests for new functionality

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Vijay M** - *Initial work* - [Your GitHub Profile]

## 🙏 Acknowledgments

- World Bank for providing the greenhouse gas emissions data
- Python community for the excellent data science libraries
- Contributors and maintainers of pandas and matplotlib

## 📞 Support

For support, please:
1. Check the [Issues](https://github.com/yourusername/greenhouse-emissions-analysis/issues) section
2. Create a new issue if your problem isn't already listed
3. Contact the maintainers at [your-email@domain.com]

## 🔄 Future Enhancements

- [ ] Add support for more data formats
- [ ] Implement interactive visualizations
- [ ] Add machine learning capabilities for emission prediction
- [ ] Create a web interface for easier data visualization
- [ ] Add support for real-time data updates

---

⭐ Star this repository if you find it useful! 
