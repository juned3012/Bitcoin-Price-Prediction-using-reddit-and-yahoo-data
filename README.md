# Bitcoin Price Prediction using reddit and yahoo data<br>
1.To develop and implement machine learning models to predict future Bitcoin price trends based on the collected data.<br>
2.To analyze sentiments from Reddit discussions to identify how public perception and notable events may have influenced Bitcoin prices<br>
3.Identify correlations and causal relationships between sentiment expressed on Reddit and Bitcoin price fluctuations to gain insights into market dynamics<br>

### Bitcoin Price Prediction Methodology

#### Data Collection
I collected data from Reddit and Yahoo Finance. Using PRAW, I scraped posts from cryptocurrency-related subreddits, capturing details like `post_id`, `title`, `selftext`, `author`, `score`, `publish_date`, and more. For financial data, I used `yfinance` to download Bitcoin prices from January 1, 2014, to May 1, 2024, including attributes such as `open`, `high`, `low`, `close`, and `volume`.

#### Sentiment Analysis
Sentiment analysis on Reddit posts involved preprocessing the text (removing apostrophes, links, special characters, etc.), tokenizing, stemming, and lemmatizing. Using TextBlob and NLTK's SentimentIntensityAnalyzer, I generated sentiment scores (polarity, subjectivity, positive, negative, neutral, compound) and classified texts as "positive", "neutral", or "negative".

#### Dataset Exploration
For the Yahoo Finance data, I converted the `date` column to datetime, removed unwanted columns, and performed basic EDA to understand the data's structure and content.

#### Data Merging
I merged the Reddit and Yahoo Finance datasets by aligning `publish_date` with `date`, resulting in a dataset with attributes like `score`, `num_of_comments`, `red_polarity`, `red_subjectivity`, `red_compound`, `open`, `high`, `low`, `close`, and `volume`.

#### Exploratory Data Analysis (EDA)
I conducted EDA on the merged dataset, plotting historical Bitcoin prices, comparing them with Reddit sentiment scores, and performing cross-correlation analysis to explore lagged relationships between sentiment and price movements.

#### Model Building
The target variable was the Bitcoin closing price. The dataset was split into training and testing sets and normalized. I implemented an LSTM neural network model with two LSTM layers and two Dense layers, compiled with MSE loss and the 'adam' optimizer. The model was trained and fine-tuned over several epochs to optimize performance.

#### Prediction
Using the trained model, I predicted Bitcoin prices, leveraging the last 60 days of closing prices to predict the price for May 1, 2024, combining historical data and social media sentiment for robust predictions.

####How to Implement 
1.
2. bitcoin_sentiment.ipynb<br>
3. prediction.ipynb<br>

