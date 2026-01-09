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
6. [Machine Learning Methods](#machine-learning-methods)
7. [Conclusion](#conclusion)
8. [Limitations and Future Work](#limitations-and-future-work)

# INTRO

Today, K-pop is more than just music, having transformed into a huge digital culture that reaches millions worldwide. Within this global culture, BTS is recognized as one of the greatest motivational forces. It is due to this reason that in an attempt to comprehend the popularity that BTS has gained, essentially, the explanation is the same as understanding the functionality of the huge digital culture that has been generated.

As the popularity of BTS expands worldwide, there is a corresponding increase in the performance of their music videos and their online engagement. Each music video release, when combined with other factors like return dates, fan engagement, and worldwide search interests, presents a data-gradable cycle of engagement. Such interaction cycles are determined by viewer engagement rates, including like rates, comment density, trending, and engagement rates. All these work in conjunction with each other to produce a complex yet interesting success formula that, when analyzed with data science, could explain the process of BTS's success at an international level and how it keeps evolving with time.

This project aims to examine BTS's global engagement model from a data science perspective. By analyzing a wealth of data, from music video performances and trend waves to the rate of like growth and comment density, I aim to uncover the key drivers of popularity with using both visualizations, statistical methods, and machine learning models, I want to show by the numbers why BTS has such a strong global impact

## Objectives

With this new scope in mind and this new set of available data, the overall objectives of this project include:

- Determine the popularity of BTS's global search over time.
- Explore the correlation between BTS’s album sales and international search interest.
- Check if the years with greater search interest result in greater album sales.
- Discuss how particular search interests, for instance, Jungkook, Jimin, V, RM, Suga, J-Hope, and Jin, differ in search volume throughout a certain period of time.
- Create simple models based on data (for example, a study of correlation or regression analysis) to examine if search interest can aid in album sales predictions.

## Motivation

The global successfulness of the group, I must admit, has always been quite interesting to learn and know. The power of influence exerted by the band not only by their musical performances but by their online presence and engagement that receives constant attention and monitoring on the internet is what has actually triggered me to learn the mathematical calculations of their popularity using actual numbers.
In this project, I will concentrate on two issues:

1. How many searches there are for "BTS" and each individual member worldwide over a period of time.
2. Sales performance of BTS albums based on estimated sales.

In other words, I would like to see if interest levels in the world (measured in the number of searches on Google) are connected to music sales (measured in the number of sales) through these two factors I have chosen. A final reason I am interested in this topic is that I love music, and I am interested in analyzing something I am passionate about.
     Note that I could measure music sales in a number of different ways; for example, I could also measure music

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

These parameters are gleaned from publicly accessible sources for album sales data (e.g., data aggregators that provide song hashtags). Once gathered from raw data sources, the data is stored within an organized CSV format for standardization to remove inconsistencies within the data set (e.g., to standardize song title names to remove variations).

This file is saved as: - `bts_album_sales.csv`: This contains the title, year, and estimated sales

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

Based on the new scope presented, the hypothesis tests are as follows:

### 1) Global Search Interest -> Album Sales

**H₀:** There is no significant relationship between BTS’s search interest from a global perspective (Google Trends value) and their album sales.

**H₁**: The higher the BTS global search interest, the more albums are sold.

This hypothesis will be tested through correlation and regression analysis between the average BTS trend scores per year and album sales.
---

### 2) Early vs. Later Eras of BTS

**H₀:** There is no significant difference in average album sales when comparing earlier BTS albums to more contemporary BTS albums.
**H₁:** The more recent BTS releases have a significantly different average sale of albums compared to the earlier ones.

Albums can be classified based on time, such as before and after the year 2017, and the sale of the albums can be compared using the correct statistical test.

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

### 6) Machine Learning Methods
For determining if global popularity metrics can account for album sales of BTS, a regression machine-learning algorithm was used.
A Linear Regression model was trained with the yearly Google Trends scores of BTS and the search interests of the members as input variables and album sales as the output. The dataset was divided into a training set and a test set.
The Linear Regression model had an R² value of 0.53, which meant that over half the data on album sales is explained by global search interest and member popularity. The mean absolute error is approximately 689,000 units. This is quite a good estimate considering the magnitude of BTS album sales.
These findings suggest that search interest is an important factor in explaining commercial performance, although there are additional factors that are also relevant.

# Conclusion
This project investigates the relationship between the global fame of BTS and the album sales by merging Google Trends search data with album sales data. Using exploratory data analysis, hypothesis testing, and basic machine learning models, the project tries to understand if online interest helps explain or predict commercial success.
Analysis actually shows that global search interest for BTS is moderately correlated with album sales, hinting that years with high public attention are more or less likely to coincide with stronger commercial performance. That might well underpin the proposal that online popularity is a major indicator of market success, though it's clearly not the only driving force when it comes to album sales.
Member-specific Google search trends also showed distinct patterns over time, where some members have persisted at higher levels of search interest. These generally moved in parallel with overall BTS popularity, which suggests that group-level attention and individual member interest are highly linked.
A basic regression in machine learning was executed to predict album sales using features that related to popularity.
 The model achieved a moderate R² score, indicating that search trends explain a meaningful portion of sales variation, but also highlighting that album performance depends on additional factors such as marketing strategies, release timing, and industry conditions that were not included in the dataset.

# Limitations and Future Work
This paper uses estimated album sales and aggregate Google Trends, which may not accurately reflect real-world customer activities. It is noted that the sample size is small, which makes it difficult to use complex models for predictions.
Further studies might involve:
To bring music video performance data into the equation
Data from streaming services or sales data in regions
Using More Advanced Models of Machine Learning
Engaging in time series analysis during the time of album releases
In conclusion, this project illustrates how an assortment of publicly available data sets can help reveal interesting information about digital popularity and performance data, as well as the fallibility of prediction through data analysis for real-world cultural occurrences.
