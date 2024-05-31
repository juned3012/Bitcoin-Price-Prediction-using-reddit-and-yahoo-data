
# Bitcoin Price Prediction using Reddit and Yahoo Finance Data

## Project Overview
This project aims to predict future Bitcoin price trends using machine learning models based on data collected from Reddit discussions and Yahoo Finance. The objectives include analyzing sentiments from Reddit discussions to understand how public perception and notable events influence Bitcoin prices and identifying correlations between sentiment expressed on Reddit and Bitcoin price fluctuations.

## Methodology

### Data Collection
Data was collected from Reddit using PRAW to scrape posts from cryptocurrency-related subreddits, capturing details such as post_id, title, selftext, author, score, publish_date, and more. Financial data, including Bitcoin prices from January 1, 2014, to May 1, 2024, was obtained using yfinance, which includes attributes such as open, high, low, close, and volume.

### Sentiment Analysis
Sentiment analysis on Reddit posts involved preprocessing text (removing apostrophes, links, special characters, etc.), tokenizing, stemming, and lemmatizing. Sentiment scores (polarity, subjectivity, positive, negative, neutral, compound) were generated using TextBlob and NLTK's SentimentIntensityAnalyzer, classifying texts as "positive," "neutral," or "negative."

### Dataset Exploration
For the Yahoo Finance data, the date column was converted to datetime, unwanted columns were removed, and basic Exploratory Data Analysis (EDA) was performed to understand the data's structure and content.

### Data Merging
The Reddit and Yahoo Finance datasets were merged by aligning publish_date with date, resulting in a dataset with attributes like score, num_of_comments, red_polarity, red_subjectivity, red_compound, open, high, low, close, and volume.

### Exploratory Data Analysis (EDA)
EDA was conducted on the merged dataset, plotting historical Bitcoin prices, comparing them with Reddit sentiment scores, and performing cross-correlation analysis to explore lagged relationships between sentiment and price movements.

### Model Building
The target variable was Bitcoin's closing price. The dataset was split into training and testing sets, normalized, and used to implement an LSTM neural network model with two LSTM layers and two Dense layers. The model was compiled with MSE loss and the 'adam' optimizer, trained, and fine-tuned over several epochs to optimize performance.

### Prediction
Using the trained model, Bitcoin prices were predicted by leveraging the last 60 days of closing prices to predict the price for May 1, 2024, combining historical data and social media sentiment for robust predictions.

### How to Implement
- **reddit_scrap.ipynb**: Jupyter notebook for scraping Reddit data.
- **bitcoin_sentiment.ipynb**: Jupyter notebook for sentiment analysis on Bitcoin-related Reddit posts.
- **prediction.ipynb**: Jupyter notebook for Bitcoin price prediction using LSTM neural networks.

---

