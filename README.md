# Meal Delivery Platform Analytics Prototype
## Data Engineering • Medallion Architecture • Star Schema • Operational Insights
This project presents an end-to-end data analytics prototype designed to help a meal delivery platform address one of its key operational challenges: **inconsistent delivery** 
times leading to customer dissatisfaction, reduced trust, and potential revenue impact.

Using a structured modern data architecture and analytical workflows, this prototype demonstrates how the delivery platform can strengthen delivery operations, 
improve customer experience, and support partner restaurants through data-driven insights.

## Project Overview
The prototype implements a complete data engineering and analytics pipeline using the **medallion architecture**:
 - **Bronze layer** - Raw ingestion of Delivery, Driver, Restaurant, and Customer data.
 - **Silver layer** - Data cleaning, null handeling, quality checks, and referential integrity enforcement.
 - **Gold layer** - **Star Schema** optimised for BI analysis and dashboards.

A set of analytical use cases is developed to address the platform's core business problems:
1. **Optimised Delivery Driver Allocation** - Analyse driver performance, distance, and efficiency to support smarter matching between order and driver.
2. **Accurate Delivery Time Estimation** - Use past delivery duration, distance, and oickup delays to refine ETA predictions.
3. **Restaurant Performance Optimisation** - Identify slow preparation times, peak-hour bottlenecks, and high-volume periods.
4. **Customer Insights** - Understand ordering patterns and behaviours to support targeted marketing and loyalty strategies.

## Architecture
### Medallion Structure
- **Bronze Layer**:
  - Raw Delivery, Driver, Restaurant, and Customer tables loaded from data sources.
  - No transtormation applied, retained for auditability
- **Silver Layer**:
  - Null handelling, data cleaning, normalisation
  - Duplicate removal, type correction, and integrity checks (check for orphaned keys)
- **Gold Layer**:
  - Modeled into a Star Schema:
    - **Fact Table**: ```fact_Delivery```
    - **Dimension Tables**: ```dim_Customer```, ```dim_Driver```, ```dim_Restaurant```
  - Tables linked using surrogate keys to improve **query performance** and dashboard responsiveness

## Analytical Dashboards
Several analytical visualisations were built, including:
- Average delay by restaurant.
- Average delivery duration by driver.
- Average delay in delivery at different time of day and suburbs
- Relationship between delivery delays and customer rating.

These insights support operational decision making and improvements in customer experience.

## Summary
This project demonstrates how a well-designed data engineering pipeline and analytical layer can significantly improve the operational efficiency of a meal delivery platform, 
customer trust, and business intelligence capabilities. By leveraging the Medallion Architecture, structured modeling, and targeted analytics, 
the solution provides a foundation for scalable, data-driven operational improvements.
