# SQL Summative Lab

A comprehensive SQL assessment project that demonstrates advanced database querying, data analysis, and visualization skills using SQLite and Python.

## Overview

This lab consists of two main parts:
1. **Guided SQL Queries** - Solving business problems for a miniature model company
2. **Exploratory Data Analysis** - Independent analysis of movie industry data

## Project Structure

```
├── SQLSummativeLab.ipynb    # Main Jupyter notebook with all analysis
├── data.sqlite               # Company database (customer/product data)
├── im.db                    # Movie database (IMDB data)
├── im.db.zip               # Compressed movie database
├── images/                  # ERD diagrams and images
│   ├── ERD.png
│   ├── movie_data_erd.jpeg
│   └── toycars.jpg
└── README.md               # This file
```

## Part 1: Guided SQL Queries

### Business Context
Analysis of a wholesale miniature models company specializing in classic cars, motorcycles, and planes. The queries address various business needs including customer segmentation, product analysis, and employee management.

### Key Queries Implemented

1. **California High-Value Customers** - Identify customers with credit limits > $25,000
2. **International Collectable Campaign** - Find non-US customers with "Collect" in company name
3. **USA Credit Analysis** - Average credit limits by state with visualization
4. **Top Customers** - Top 10 customers by total payments with visualization
5. **Product Quantity Analysis** - Customers purchasing 10+ units of products
6. **Product Line Analysis** - Relationship between product variety and sales volume
7. **Remote Office Candidates** - Employees in offices with < 5 employees

### Technical Skills Demonstrated
- Complex JOIN operations
- Aggregate functions (COUNT, AVG, SUM)
- GROUP BY and HAVING clauses
- Subqueries
- Data visualization with matplotlib/seaborn
- Business-oriented SQL query design

## Part 2: Exploratory Movie Analysis

### Dataset
- **Source**: IMDB movie data
- **Time Period**: 2010-2019
- **Tables**: movie_basics, movie_ratings, directors, writers, persons, principals, etc.

### Data Cleaning Challenges Addressed

1. **Missing Values**
   - 5,359 movies (3.7%) missing genre information
   - 30,765 movies (21.2%) missing runtime data
   - 71,225 movies (49.1%) missing rating data

2. **Data Quality Issues**
   - Extreme runtime outliers (1 minute to 51,420 minutes)
   - Inconsistent genre formatting (single vs multi-genre)
   - Rating reliability (need minimum vote thresholds)

3. **Cleaning Solutions**
   - Applied realistic runtime bounds (30-300 minutes)
   - Filtered for movies with ≥100 votes
   - Focused on single-genre movies for cleaner analysis
   - Removed records with missing critical fields

### Business Question Analysis

**Research Question**: Does longer runtime correlate with higher audience ratings, and does this relationship differ across genres?

**Key Findings**:
- Correlation varies significantly by genre
- Some genres show positive runtime-rating correlation
- Others show little to no relationship
- Genre-specific insights for production decisions

## Reflection Questions

The notebook includes detailed reflection questions that explain:

1. **WHERE Clause Logic** - Technical explanation for non-technical managers
2. **Visualization Choices** - Rationale for scatter plot selection in product analysis
3. **Subquery Design** - Step-by-step explanation of remote office query logic

## Technical Requirements

### Dependencies
```python
import sqlite3
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import zipfile
```

### Database Connections
- **Company Data**: `sqlite3.connect('data.sqlite')`
- **Movie Data**: `sqlite3.connect('im.db')`

## Key Learnings

### SQL Skills
- Advanced JOIN strategies for multi-table queries
- Subquery optimization for complex filtering
- Aggregate function combinations for business metrics
- Data filtering and validation in SQL

### Data Analysis
- Identifying and addressing data quality issues
- Correlation analysis across different dimensions
- Visualization selection based on data characteristics
- Business question formulation from exploratory findings

### Business Intelligence
- Translating business requirements into technical queries
- Presenting technical findings to non-technical stakeholders
- Data-driven decision making frameworks
- Industry-specific analysis (retail vs entertainment)

## Usage Instructions

## Setup Environment
   ```bash
   # Create virtual environment
   python -m venv .venv
   source .venv/bin/activate  
   
   # Install dependencies
   pip install pandas matplotlib seaborn jupyter
   ```

## Business Impact

### Retail Company Insights
- **Customer Segmentation**: Identified high-value customers for targeted marketing
- **Product Strategy**: Analysis of product line performance for inventory decisions
- **Operational Efficiency**: Remote work recommendations based on office size

### Movie Industry Insights
- **Production Strategy**: Runtime optimization recommendations by genre
- **Data Quality Framework**: Systematic approach to cleaning large datasets
- **Analytical Methodology**: Reproducible process for exploratory analysis

## Future Enhancements

### Potential Extensions
1. **Predictive Modeling**: Build models to predict movie success
2. **Time Series Analysis**: Analyze trends across the 2010-2019 period
3. **Geographic Analysis**: Incorporate regional preferences in movie data
4. **Advanced Visualizations**: Interactive dashboards for business users

### Data Improvements
1. **Additional Sources**: Integrate box office data, streaming metrics
2. **Real-time Updates**: Set up automated data pipelines
3. **Cross-validation**: Verify findings against external datasets


