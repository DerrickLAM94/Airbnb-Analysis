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

Let me know if you have any other questions! Contributions to analyze additional aspects are welcome.

## Sentiment Analysis
<img width="875" alt="情感分析" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/0f08b767-5cd8-462c-b13f-33476b3dd7e8">

-
<img width="633" alt="Airbnb-statment" src="https://github.com/DerrickLAM94/Airbnb-Analysis/assets/140989898/c9b26eaa-f3b9-4b66-93bf-8a8c8628c125">

This is a sentiment analysis based on each comment to analyze the content of the comment as positive, negative or neutral. The results show that over 50,000 comments reflect positively, indicating a better guest experience. Only less than 2,000 comments are negative. However, over 40,000 comments are neutral. This reflects an experience that is neither good nor bad. Airbnb should focus on researching how to convert these neutral comments into positive ones.
such as 
- Targeted follow-up surveys - Reach out to users who left neutral comments and ask tailored questions to understand what could have been improved. This feedback can then be used to enhance the listing/host experience.
- Sentiment analysis of reviews - Utilize NLP tools to analyze semantic sentiment in neutral reviews. Identify aspects commonly mentioned positively that could be emphasized to tilt the review upwards.
