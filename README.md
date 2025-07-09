# Advanced Big Data and Data Mining - Lab 1

##  Information
- **Course**: Advanced Big Data and Data Mining
- **Assignment**: Lab 1 - Data Visualization, Data Preprocessing, and Statistical Analysis
- **Dataset**: Bank Customer Churn Prediction

## Purpose of Lab Work

This lab demonstrates fundamental data science techniques using Python in Jupyter Notebook environment. The primary objectives include:

1. **Data Exploration**: Loading and understanding the structure of a bank customer dataset
2. **Data Visualization**: Creating meaningful charts and plots to explore relationships and patterns
3. **Data Preprocessing**: Cleaning, transforming, and preparing data for analysis
4. **Statistical Analysis**: Computing descriptive statistics and correlation measures

The lab uses a bank customer churn dataset containing 10,000 records with 12 features including customer demographics, account information, and churn status.

## Key Insights from Visualizations

### Data Distribution Insights:
- **Age vs Balance**: The scatter plot reveals that customers across all age groups have varying balance amounts, with no strong linear relationship
- **Average Balance by Age**: Shows fluctuating average balances across different ages, with some peaks in middle-aged customers
- **Product Distribution**: Most customers (majority) have only 1 product, with decreasing numbers having 2, 3, or 4 products
- **Credit Score Distribution**: Approximately normal distribution centered around 650, ranging from 350 to 850
- **Balance by Gender**: Box plot shows similar median balances between male and female customers
- **Country Distribution**: Customers are distributed across France, Germany, and Spain with relatively balanced representation

### Customer Behavior Patterns:
- **Churn Rate**: 20.37% of customers have churned, indicating a significant retention challenge
- **Age Groups**: Adult customers (30-40) represent the largest segment, followed by middle-aged customers
- **Balance Categories**: Most customers fall into the "High" balance category (50K-100K), with fewer in extreme low or very high categories

## Statistical Analysis Findings

### Central Tendency Measures:
- **Average Age**: 38.92 years (median: 37 years)
- **Average Credit Score**: 650.53 (median: 652)
- **Average Balance**: €76,485.89 (median: €97,198.54)
- **Average Tenure**: 5.01 years (median: 5 years)
- **Average Estimated Salary**: €100,090.24

### Dispersion Analysis:
- **Age Range**: 74 years (18-92), with standard deviation of 10.49
- **Credit Score Range**: 500 points, with standard deviation of 96.65
- **Balance Variability**: High standard deviation (€62,397.41) indicates significant variation in customer balances

### Correlation Analysis:
- **Strongest Positive Correlation**: Age and Churn (0.285) - older customers more likely to churn
- **Notable Negative Correlation**: Balance and Products Number (-0.304) - customers with more products tend to have lower balances
- **Active Members and Churn**: Negative correlation (-0.156) - active members less likely to churn

## Challenges Faced and Decisions Made

### Data Preprocessing Challenges:

1. **Missing Values Handling**:
   - **Challenge**: Original dataset had no missing values, limiting demonstration of handling techniques
   - **Solution**: Artificially introduced missing values (100 in balance, 50 in credit_score) to demonstrate various imputation methods
   - **Decision**: Used mean imputation for balance and median for credit_score to handle skewed distributions

2. **Outlier Detection**:
   - **Challenge**: IQR method showed no outliers in balance column due to the data distribution
   - **Decision**: Maintained the IQR approach as it's robust for this type of financial data
   - **Insight**: Lower bound was negative (-191,466.36), which is acceptable for account balances

3. **Data Scaling**:
   - **Challenge**: Features had different scales (age: 18-92, balance: 0-250K, salary: 11-200K)
   - **Solution**: Applied Min-Max scaling to normalize all numeric features to 0-1 range
   - **Decision**: Chose Min-Max over StandardScaler to maintain interpretability

4. **Discretization Decisions**:
   - **Age Groups**: Created 5 meaningful categories (Young, Adult, Middle-aged, Senior, Elderly)
   - **Balance Categories**: Defined 4 tiers based on financial service industry standards
   - **Challenge**: Balancing granularity with interpretability

### Technical Decisions:

1. **Visualization Choices**:
   - Selected 6 different plot types to meet requirements while providing comprehensive data exploration
   - Used seaborn styling for professional appearance
   - Implemented subplot layout for efficient space utilization

2. **Statistical Analysis**:
   - Computed comprehensive measures including central tendency, dispersion, and correlation
   - Created correlation heatmap for better visualization of relationships
   - Included both parametric and non-parametric measures

3. **Data Reduction**:
   - **Sampling**: Reduced dataset to 80% (8,000 records) to demonstrate sampling techniques
   - **Dimension Reduction**: Removed customer_id as it provides no analytical value
   - **Rationale**: Maintained data integrity while reducing computational complexity


## Key Takeaways

1. **Data Quality**: The dataset was well-structured with no missing values, requiring simulation for preprocessing demonstration
2. **Customer Insights**: Age appears to be the strongest predictor of churn, followed by account activity
3. **Balance Patterns**: Customer balances show high variability, suggesting diverse customer segments
4. **Preprocessing Importance**: Proper scaling and handling of categorical variables essential for further analysis
5. **Statistical Relationships**: Weak to moderate correlations suggest complex, non-linear relationships in customer behavior


## Tools and Libraries Used

- **pandas**: Data manipulation and analysis
- **numpy**: Numerical operations
- **matplotlib**: Basic plotting
- **seaborn**: Statistical data visualization
- **scipy.stats**: Statistical functions
- **sklearn.preprocessing**: Data scaling and transformation


*This lab successfully demonstrates the complete data science pipeline from raw data to actionable insights, providing a solid foundation for advanced analytics and machine learning applications.*
