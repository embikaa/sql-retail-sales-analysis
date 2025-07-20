# Retail Sales Data Analysis SQL Project

## Overview
This project demonstrates comprehensive SQL data analysis techniques using a retail sales dataset. The project covers database creation, data cleaning, exploration, and business intelligence queries to extract meaningful insights from retail transaction data.

## Database Schema

### Table: retail_sales
```sql
transactions_id   INT PRIMARY KEY
sale_date         DATE
sale_time         TIME
customer_id       INT
gender            VARCHAR(15)
age               INT
category          VARCHAR(15)
quantity          INT
price_per_unit    FLOAT
cogs              FLOAT
total_sale        FLOAT
```

## File Structure

```
retail-sales-analysis/
│── SQL - Retail Sales Analysis_utf
├── README.md
└── sql_retail.sql
```

## Project Structure

### 1. Database Setup
- Database creation (`Sales`)
- Table schema definition with appropriate data types
- Primary key configuration

### 2. Data Cleaning
- Identification of NULL values across all columns
- Data quality assessment
- Removal of incomplete records to ensure data integrity

### 3. Data Exploration
- **Total Sales Count**: Overview of transaction volume
- **Unique Customers**: Customer base analysis
- **Product Categories**: Available product categories in the dataset

### 4. Business Intelligence Analysis

#### Key Business Questions Solved:

1. **Daily Sales Analysis**
   - Retrieve all sales for specific dates
   - Filter transactions by date ranges

2. **Category & Quantity Analysis**
   - Filter sales by product category and quantity thresholds
   - Monthly transaction filtering

3. **Revenue Analysis**
   - Calculate total sales per category
   - Identify high-value transactions (>$1000)

4. **Customer Demographics**
   - Average customer age by product category
   - Gender-based transaction analysis per category

5. **Top Performers**
   - Best-selling months per year using window functions
   - Top 5 customers by total purchase value
   - Unique customers per category

6. **Time-based Analysis**
   - Sales distribution by time shifts:
     - Morning: Before 12 PM
     - Afternoon: 12 PM - 5 PM
     - Evening: After 5 PM

## Key SQL Techniques Demonstrated

- **Data Definition Language (DDL)**: Database and table creation
- **Data Manipulation Language (DML)**: Data cleaning and deletion
- **Aggregate Functions**: COUNT, SUM, AVG
- **Date/Time Functions**: EXTRACT, TO_CHAR
- **Window Functions**: RANK() OVER()
- **Common Table Expressions (CTEs)**
- **CASE statements** for conditional logic
- **GROUP BY** with multiple columns
- **Subqueries** and derived tables

## Sample Insights

### Sales Performance
- Total number of transactions and unique customers
- Revenue breakdown by product categories
- Seasonal trends and best-performing months

### Customer Analysis
- Demographic insights (age, gender) by product preferences
- Customer purchasing behavior patterns
- High-value customer identification

### Operational Insights
- Peak sales hours and shift-based performance
- Product category popularity
- Transaction size distribution

## Getting Started

1. **Prerequisites**
   - PostgreSQL, MySQL, or any SQL-compatible database
   - SQL client or command-line interface

2. **Setup Instructions**
   ```sql
   -- Run the provided SQL script
   -- Ensure your dataset matches the table schema
   -- Execute queries in sequence for best results
   ```

3. **Data Requirements**
   - Retail sales transaction data
   - Columns matching the defined schema
   - Date range: Includes 2022 data (sample queries reference 2022)

## Usage Examples

### Find Top Performing Categories
```sql
SELECT 
    category,
    SUM(total_sale) as net_sale,
    COUNT(*) as total_orders
FROM retail_sales
GROUP BY category
ORDER BY net_sale DESC;
```

### Analyze Customer Demographics
```sql
SELECT 
    category,
    gender,
    COUNT(*) AS total_transactions,
    ROUND(AVG(age)) as avg_age
FROM retail_sales
GROUP BY category, gender;
```

## Future Enhancements

- **Advanced Analytics**: Cohort analysis, customer lifetime value
- **Data Visualization**: Integration with BI tools
- **Predictive Modeling**: Sales forecasting queries
- **Performance Optimization**: Index creation and query optimization
- **Data Pipeline**: Automated data cleaning and validation

## Technologies Used

- **SQL**: Core analysis language
- **Database**: PostgreSQL/MySQL compatible
- **Functions**: Window functions, CTEs, date/time manipulation

## Contributing

Feel free to fork this project and submit pull requests for:
- Additional business intelligence queries
- Performance optimizations
- Extended data analysis scenarios
- Documentation improvements

## License

This project is open source and available under the [MIT License](LICENSE).

---

**Note**: This project is designed for educational and analytical purposes. Ensure your actual dataset matches the schema requirements before running the queries.
