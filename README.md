# KPOP-BTS-Data-Project-DSA210


## Table of Contents

1. [INTRO](#intro)
2. [Objectives](#objectives)
3. [Motivation](#motivation)
4. [Data Collection](#data-collection)
   - [Music Video & Performance Data](#music-video--performance-data-primary-dataset)
   - [Google Trends Popularity Data](#google-trends-popularity-data-enrichment-dataset)
   - [Data Cleaning & Integration](#data-cleaning--integration)
   - [Final Dataset Structure](#final-dataset-structure)
5. [Hypothesis Testing](#hypothesis-testing)
6. [Conclusion](#conclusion)


# INTRO

K-pop today is far more than a music genre; it has grown into an enormous digital culture that reaches millions across the world. Within this global movement, BTS stands out as one of the strongest driving forces. Because of this trying to understand BTS’s popularity is essentially the same as trying to understand how modern digital culture works and how big online engagement is formed.

As BTS grows globally, both the performance of their music videos and their online engagement increased significantly over time. Each music video (MV) release when considered together with factors such as comeback timing, online fan reactions, and global search interest, creates a measurable cycle of interest. This cycle is shaped by viewer growth rates, like rates, comment density, trending trends, and release strategies. All these factors combine to form a complex yet fascinating success model that can be analyzed with data science to understand how BTS's global popularity was created and how it has changed over time.

This project aims to examine BTS's global engagement model from a data science perspective. By analyzing a wealth of data, from music video performances and trend waves to the rate of like growth and comment density, I aim to uncover the key drivers of popularity with using both visualizations, statistical methods, and machine learning models, I want to show by the numbers why BTS has such a strong global impact

## Objectives

With the updated scope and available data, the main objectives of this project are:

- Identify how BTS’s global search popularity evolves over time.
- Analyze the relationship between BTS’s album sales and global search interest.
- Examine whether years with higher search interest correspond to higher album sales.
- Explore how member-specific search interest (e.g., Jungkook, Jimin, V, RM, Suga, J-Hope, Jin) changes over time and how it overlaps with group activity periods.
- Build simple data-driven models (e.g., correlation analysis or regression) to see whether search interest can help explain or predict album sales.

## Motivation

BTS's global success has always been fascinating to me. I am intrigued by how a group can influence the world not only through their music, but also through their digital presence and the constant attention they receive online. That is why I want to understand the numerical dynamics behind BTS's popularity using real data.

In this project, I focus on two main aspects:
1. How much people search for BTS and each member globally over time.
2. How BTS albums perform in terms of estimated sales.

By combining these two dimensions, I aim to see whether changes in global interest (measured through Google search trends) are reflected in album sales performance. I am motivated both by analyzing a topic I love and by applying the data analysis techniques I have learned to a real-life example.

## Data Collecting

To analyze BTS’s global popularity and performance, I use two main types of data:

1. **Album sales data** – to represent commercial performance.
2. **Google search trends data** – to represent global interest and attention for BTS and the members.

All data is collected from publicly available online sources and stored as CSV files within the project repository.

### Album Sales Data (Primary Dataset)

The primary performance dataset consists of estimated BTS album sales. For each album, I collect:

- Album title  
- Release year  
- Estimated total sales  

These values are taken from publicly available album sales sources (such as chart and sales aggregation websites). After collecting the raw values, they are entered into a structured CSV file and cleaned for consistency (e.g., standardizing album names and ensuring numeric sales values).

This file is stored as:

- `bts_album_sales.csv` — BTS album titles, release years, and estimated sales.

### Google Trends Popularity Data (Member & Group Popularity)

To capture global attention patterns over time, I use Google Trends data. I export official Google Trends statistics for:

- “BTS”
- “Jungkook”
- “Jimin”
- “V”
- “RM”
- “Suga”
- “J-Hope”
- “Jin”

For each keyword, I download the worldwide search interest over time as CSV files. These files typically contain:

- Time (weekly or monthly resolution)
- Search interest score (0–100 scale)

These files are stored as:

- `bts_trends.csv` — search interest over time for “BTS”
- `bts_member_trends.csv` (or separate files per member) — search interest over time for individual members

### Data Cleaning & Integration

After collecting all datasets, I apply the following steps:

- **Standardize date formats** in all trends files to ensure they can be grouped or merged by year.
- **Create a “Year” variable** for both album sales and trends data to allow yearly aggregation.
- **Convert sales values** into numeric format (e.g., removing commas and converting strings to integers).
- **Aggregate Google Trends data** by year, for example by computing the average annual search interest for:
  - BTS as a group  
  - Each individual member  

Based on this, I prepare an integrated dataset where:

- Each album has:
  - Release year  
  - Estimated sales  
  - The corresponding yearly BTS trend score (and, optionally, summary statistics of member trend scores for that year)

### Final Dataset Structure

After preprocessing, the main datasets used in the project are:

- `bts_album_sales.csv` — Album title, release year, estimated sales  
- `bts_trends.csv` — Global search interest over time for “BTS”  
- `bts_member_trends.csv` (or multiple files) — Global search interest over time for individual members  
- `merged_bts_trends_sales.csv` — A combined dataset that links album sales with yearly search interest scores

This merged dataset will be used for exploratory data analysis, visualizations, and hypothesis testing.

## Hypothesis Testing

Given the updated data scope, the hypothesis tests are defined as follows:

### 1) Global Search Interest → Album Sales

**H₀:** There is no significant relationship between BTS’s global search interest (Google Trends score) and album sales.  
**H₁:** Higher BTS global search interest is associated with significantly higher album sales.

This will be tested using correlation analysis and simple regression between yearly average BTS trend scores and album sales.

---

### 2) Early vs. Later Eras of BTS

**H₀:** There is no significant difference in average album sales between earlier BTS releases and more recent BTS releases.  
**H₁:** More recent BTS releases have significantly different (higher or lower) average album sales compared to earlier releases.

Albums can be split into two or more time periods (for example, pre-2017 vs. 2017 and later), and their sales can be compared using appropriate statistical tests.

---

### 3) Member Popularity Over Time

**H₀:** Member-specific search interest (e.g., Jungkook, Jimin, V, RM, Suga, J-Hope, Jin) does not show any systematic change over time.  
**H₁:** There are significant changes or trends in member-specific search interest over time (e.g., certain members becoming more searched in specific periods).

This can be explored using trend analysis and visualizations of each member’s Google Trends time series.

---

### 4) Group Popularity vs. Member Popularity

**H₀:** BTS group search interest is not associated with member-specific search interest.  
**H₁:** Higher BTS group search interest coincides with higher search interest for individual members.

This can be tested by computing correlations between the “BTS” trend series and each member’s trend series.

---

### 5) Predicting Album Sales from Popularity Indicators

**H₀:** BTS album sales cannot be explained by a model using global search interest as an input.  
**H₁:** A simple predictive model using BTS global search interest (and possibly time variables) explains a significant portion of the variation in album sales.

A basic regression or similar model can be built using variables such as release year and trend scores as predictors, and album sales as the target.

# Conclusion
By the end of this project, I hope to answer:
Do global search trends correlate with the performance of BTS music videos?
Are certain comeback periods or release strategies associated with higher engagement?
Do music videos with faster early growth (views, likes, comments) become more successful in the long term?
How do fan behavior and online interest fluctuate before and after major BTS releases?
Can we identify the key features that most strongly predict whether a BTS MV will go viral?
Is it possible to build a machine learning model that predicts MV performance based on early metrics and trend activity?
Through this project, I aim to better understand the digital dynamics behind BTS’s global popularity. By combining statistical analysis, data visualization, and machine learning
