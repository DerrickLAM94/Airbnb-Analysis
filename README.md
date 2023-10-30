# Airbnb Listing Analysis

This repository contains Jupyter notebooks and code for analyzing Airbnb listing data. The goal is to gain insights into pricing, locations, and other factors that impact Airbnb listings. 

## Data

The data used for this analysis comes from insideairbnb.com. It contains listing details for thousands of Airbnb listings across multiple cities. The specific data files analyzed are:

- listings.csv - Details of individual listings like price, reviews, property type
- calendar.csv - Available dates and pricing for each listing
- reviews.csv - Reviews left by guests for each listing

## Analysis

The Jupyter notebooks in this repository explore different aspects of the data:

- listings_exploration.ipynb - Basic EDA of listings data, examining top cities, average prices etc.  
- calendar_analysis.ipynb - Analysis of booking patterns and impact of dates/seasons on pricing
- reviews_sentiment.ipynb - Sentiment analysis of text reviews to understand driver of positive reviews
- cross_city_comparison.ipynb - Comparing listing attributes and pricing across different cities

## Requirements

The notebooks require Python 3 and the following libraries:

- Pandas 
- NumPy
- Matplotlib 
- Seaborn
- NLTK (for sentiment analysis)
- WordCloud

## Data Sources
The data used for this analysis comes from:
insideairbnb.com - This site scrapes listing data directly from Airbnb and provides it in bulk for analysis. Data includes listings, calendar availability and reviews. New data is added quarterly.
http://insideairbnb.com/get-the-data/ - This page on Inside Airbnb allows downloading the raw data files for HongKong.

Let me know if you have any other questions! Contributions to analyze additional aspects are welcome.

## --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Processing The Data

<img width="913" alt="螢幕截圖 2023-10-30 下午2 00 21" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/ed39f11c-6093-429a-a815-3e164478b30f">
- Drops the column reviews_per_month from the Data dataframe, and assigns the resulting dataframe to Data2. The drop() function removes specified labels from rows or columns.
- Fills any missing values in the Review dataframe with 0 using the fillna() function. The inplace=True argument means that the changes are made directly in the Review dataframe, without creating a new dataframe.
- Checks for duplicated rows in the Data2 dataframe using the duplicated().sum() function. This returns the total number of duplicated rows.


## Sentiment Analysis
<img width="875" alt="情感分析" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/0f08b767-5cd8-462c-b13f-33476b3dd7e8">

<img width="999" alt="statment_result" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/7927574d-5837-42c2-a943-fffa0f59943e">


-
<img width="633" alt="Airbnb-statment" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/c9b26eaa-f3b9-4b66-93bf-8a8c8628c125">

This is a sentiment analysis based on each comment to analyze the content of the comment as positive, negative or neutral. The results show that over 50,000 comments reflect positively, indicating a better guest experience. Only less than 1,548 comments are negative. However, over 40,000 comments are neutral. This reflects an experience that is neither good nor bad. Airbnb should focus on researching how to convert these neutral comments into positive ones.

- Targeted follow-up surveys - Reach out to users who left neutral comments and ask tailored questions to understand what could have been improved. This feedback can then be used to enhance the listing/host experience.
- Sentiment analysis of reviews - Utilize NLP tools to analyze semantic sentiment in neutral reviews. Identify aspects commonly mentioned positively that could be emphasized to tilt the review upwards.

## WordCloud
<img width="795" alt="wordcloud" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/55f15dbe-ed76-4017-a83a-6c221e1677c7">

From this, we can see:
- In positive reviews, the most frequent words are "place", "clean", etc. This likely indicates that guests were satisfied with the convenience of the accommodation location and that the home itself was clean.

- Meanwhile, in negative reviews, the most common words are "room" and "small", etc. This likely suggests that guests found the living space of the accommodation to be too small and did not meet their expectations.

- Therefore, the results of this word cloud analysis show that factors such as remote locations or living spaces being too small can negatively impact guest satisfaction. In contrast, convenient geographical locations and clean, tidy living environments tend to leave guests with a more positive impression.

- Airbnb may be able to advise hosts based on these findings to pay more attention to housing quality and practicality, especially space configuration, in order to improve service quality and customer experience.

## CORRELATION ANALYSIS

Correlation analysis: The corr() method in pandas can be used to calculate the Pearson correlation coefficient (-1 to 1) between each pair of variables. Positive correlation means that as one variable increases, so does the other; negative correlation means that as one variable increases, the other decreases. Correlation close to 0 indicates almost no linear relationship between the two variables.
<img width="849" alt="螢幕截圖 2023-10-27 下午2 06 56" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/04c2618f-f28b-41ff-aeeb-c0fa9921619d">
<img width="318" alt="螢幕截圖 2023-10-27 下午2 09 54" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/81b9a5a6-8e63-42ed-a49b-4eeb3adbb495">

- The correlations of id and host_id with price are close to 0, indicating almost no linear relationship between these variables and price.

- The correlation of latitude with price is 0.018431, which is a very small positive value, so we can say the relationship between latitude - and price is extremely weak, but there is a slight tendency for price to increase as latitude increases.

- The correlation of longitude with price is -0.064905, which is a small negative value, indicating a slight tendency for price to decrease as longitude increases, but this relationship is still very weak.

- The correlations of minimum_nights, reviews_per_month, calculated_host_listings_count and availability_365 with price are all negative, indicating a slight tendency for price to decrease as these variables increase. Among these variables, 
  calculated_host_listings_count has the strongest correlation with price (-0.141563), but it is still relatively weak.  

- The correlations of number_of_reviews and number_of_reviews_ltm with price are close to 0, indicating almost no linear relationship between these variables and price.

## HeatMap

I want to understand which areas have more popular listings (e.g. more reviews)
![螢幕截圖 2023-10-27 下午3 04 57](https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/f0b848bd-74d5-4e5d-8268-7f67d08609be)

- The results reflect that guests staying in Hong Kong are concentrated in Kowloon and the New Territories, which makes sense. The main tourist areas in Hong Kong are located in those regions.

- The heatmap shows more intense clusters of highly reviewed listings in areas like Tsim Sha Tsui, Mong Kok, and Lantau Island. This indicates that popular tourist destinations like Tsim Sha Tsui in Kowloon and Lantau Island, home to attractions like   the Big Buddha, have more popular and highly reviewed Airbnb listings. 

- The Hong Kong Island area shows fewer clusters, likely because there are fewer tourist attractions. The urban density of Hong Kong Island also means there are fewer available Airbnb listings compared to more suburban areas. 

- So in summary, the geographic distribution of popular and highly reviewed listings on the heatmap aligns with the layout of Hong Kong's major tourist regions, with heavy concentrations in Kowloon and the New Territories near the most visited     
  attractions. This reflects where most guests are traveling within Hong Kong.


