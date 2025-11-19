# KPOP-BTS-Data-Project-DSA210

# INTRO

K-pop today is far more than a music genre; it has grown into an enormous digital culture that reaches millions across the world. Within this global movement, BTS stands out as one of the strongest driving forces. Because of this trying to understand BTS’s popularity is essentially the same as trying to understand how modern digital culture works and how big online engagement is formed.

As BTS grows globally, both the performance of their music videos and their online engagement increased significantly over time. Each music video (MV) release when considered together with factors such as comeback timing, online fan reactions, and global search interest, creates a measurable cycle of interest. This cycle is shaped by viewer growth rates, like rates, comment density, trending trends, and release strategies. All these factors combine to form a complex yet fascinating success model that can be analyzed with data science to understand how BTS's global popularity was created and how it has changed over time.

This project aims to examine BTS's global engagement model from a data science perspective. By analyzing a wealth of data, from music video performances and trend waves to the rate of like growth and comment density, I aim to uncover the key drivers of popularity with using both visualizations, statistical methods, and machine learning models, I want to show by the numbers why BTS has such a strong global impact

# Motivation
BTS's global success has always been fascinating to me. Im intrigued by how a group can change the world so much not just through their music but also through their impact on digital platforms. Thats the reason why I want to understand the numerical dynamics behind BTS's popularity. I want to use data science to examine which music videos get the most attention and why, how trends shift with comebacks, and how fan interaction influences popularity. I'm motivated both by analyzing a topic I love and by applying the techniques I have learned to a real life example.

# Data Collecting

To analyze BTS’s global popularity and performance dynamics, I will collect data from publicly availableonline sources. My data collection process will include two main components: performance datas and global trend datas. All data will be gathered using verified platforms and stored in organized CSV files within the project repository.
1. ## Music Video & Performance Data (Primary Dataset)
I will gather detailed BTS music video performance metrics from public datasets on platforms such as Kaggle and YouTube-based datasets. These datasets typically include:
Music video titles
Release dates
Total and daily view counts
Like / dislike ratios
Comment counts
Video duration
Engagement growth over time
These files will be downloaded in CSV format and cleaned for consistency (unified date formats, numeric conversions, and removing missing or duplicated entries).

2. ## Google Trends Popularity Data (Enrichment Dataset)
To capture global attention patterns, I will export official Google Trends data for keywords such as:

“BTS”

“Jungkook”

“Jimin”

“V”

“RM”

“Suga”

“J-Hope”

“Jin”

For each keyword, I will download the monthly worldwide popularity score as a CSV file. These files contain:

Time (monthly resolution)

Global trend score (0–100 scale)

Regional popularity distribution (optional)

Trend data will be aligned with music video release dates to observe interest spikes around comeback periods.

3. ## Data Cleaning & Integration

After collecting all datasets, I will:

Standardize date formats to enable time-based merging

Normalize column names across files

Convert view counts, likes, and comments into numeric format

Create new derived features (growth rate, engagement ratio, trend-at-release)

Merge Google Trends data with MV performance data through shared time indices

4. ## Final Dataset Structure
After preprocessing, the dataset will be organized into files such as:

bts_mvs.csv — Music video performance data

bts_daily_views.csv — Daily view growth (if available)

bts_trends.csv — Global trend popularity scores

merged_bts_data.csv — Final combined dataset for analysis
# Hypothesis testing

1) ## Trend Popularity → MV Performance
H₀: There is no significant relationship between Google Trends popularity and the total view count of BTS music videos.
H₁: Higher Google Trends popularity is associated with significantly higher total view counts of BTS music videos.

2) ## Early Performance → Long-Term Success
H₀: Early engagement metrics (views, likes in the first 24 hours) do not significantly influence the long-term performance of a music video.
H₁: Music videos with stronger early engagement achieve significantly higher long-term total views.

3) ## Comeback Timing Effect
H₀: There is no difference in engagement between videos released during comeback periods and videos released outside comeback periods.
H₁: BTS music videos released during comeback periods show significantly higher engagement levels.

4) ## Member Popularity → Engagement Metrics
H₀: Member-specific search interest (e.g., Jungkook, Jimin, V, RM, Suga, J-Hope, Jin) is not related to MV engagement metrics such as like ratio or comment count.
H₁: Higher member search interest is associated with higher engagement metrics in BTS music videos.

5) ## Video Characteristics → Virality
H₀: Video characteristics such as release year, video length, and category have no significant effect on whether a BTS music video becomes viral.
H₁: Specific video characteristics significantly influence the likelihood of a BTS music video becoming viral.

# Conclusion
By the end of this project, I hope to answer:
Do global search trends correlate with the performance of BTS music videos?
Are certain comeback periods or release strategies associated with higher engagement?
Do music videos with faster early growth (views, likes, comments) become more successful in the long term?
How do fan behavior and online interest fluctuate before and after major BTS releases?
Can we identify the key features that most strongly predict whether a BTS MV will go viral?
Is it possible to build a machine learning model that predicts MV performance based on early metrics and trend activity?
Through this project, I aim to better understand the digital dynamics behind BTS’s global popularity. By combining statistical analysis, data visualization, and machine learning
