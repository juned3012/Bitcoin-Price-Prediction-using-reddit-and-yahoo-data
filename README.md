# Bitcoin Price Prediction using Reddit and Yahoo Finance Data

Welcome to the **Bitcoin Price Prediction** project, where we leverage machine learning models to predict Bitcoin price trends using data from Reddit discussions and Yahoo Finance. This project explores the influence of public sentiment on Bitcoin prices and aims to provide robust price predictions.

## Table of Contents
- [Project Overview](#project-overview)
- [Methodology](#methodology)
  - [Data Collection](#data-collection)
  - [Sentiment Analysis](#sentiment-analysis)
  - [Dataset Exploration](#dataset-exploration)
  - [Data Merging](#data-merging)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Model Building](#model-building)
  - [Prediction](#prediction)
- [How to Implement](#how-to-implement)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project aims to predict future Bitcoin price trends using machine learning models based on data collected from Reddit discussions and Yahoo Finance. The objectives include analyzing sentiments from Reddit discussions to understand how public perception and notable events influence Bitcoin prices and identifying correlations between sentiment expressed on Reddit and Bitcoin price fluctuations.

## Methodology

### Data Collection

- **Reddit Data**: Collected using PRAW to scrape posts from cryptocurrency-related subreddits, capturing details such as `post_id`, `title`, `selftext`, `author`, `score`, `publish_date`, and more.
- **Financial Data**: Collected using `yfinance`, including Bitcoin prices from January 1, 2014, to May 1, 2024, with attributes such as `open`, `high`, `low`, `close`, and `volume`.

### Sentiment Analysis

- Preprocessed text (removing apostrophes, links, special characters, etc.), tokenized, stemmed, and lemmatized.
- Generated sentiment scores (polarity, subjectivity, positive, negative, neutral, compound) using TextBlob and NLTK's SentimentIntensityAnalyzer, classifying texts as "positive," "neutral," or "negative."

### Dataset Exploration

- Converted the date column to datetime, removed unwanted columns, and performed basic Exploratory Data Analysis (EDA) on the Yahoo Finance data to understand its structure and content.

### Data Merging

- Merged the Reddit and Yahoo Finance datasets by aligning `publish_date` with `date`, resulting in a dataset with attributes like `score`, `num_of_comments`, `red_polarity`, `red_subjectivity`, `red_compound`, `open`, `high`, `low`, `close`, and `volume`.

### Exploratory Data Analysis (EDA)

- Conducted EDA on the merged dataset, plotting historical Bitcoin prices, comparing them with Reddit sentiment scores, and performing cross-correlation analysis to explore lagged relationships between sentiment and price movements.

### Model Building

- The target variable was Bitcoin's closing price.
- Split the dataset into training and testing sets, normalized, and used to implement an LSTM neural network model with two LSTM layers and two Dense layers.
- Compiled the model with MSE loss and the 'adam' optimizer, trained, and fine-tuned over several epochs to optimize performance.

### Prediction

- Using the trained model, predicted Bitcoin prices by leveraging the last 60 days of closing prices to predict the price for May 1, 2024, combining historical data and social media sentiment for robust predictions.

## How to Implement

- `reddit_scrap.ipynb`: Jupyter notebook for scraping Reddit data.
- `bitcoin_sentiment.ipynb`: Jupyter notebook for sentiment analysis on Bitcoin-related Reddit posts.
- `prediction.ipynb`: Jupyter notebook for Bitcoin price prediction using LSTM neural networks.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
    ```sh
    git clone https://github.com/juned3012/Bitcoin-Price-Prediction.git
    ```

2. Navigate to the project directory:
    ```sh
    cd Bitcoin-Price-Prediction
    ```

3. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

To scrape Reddit data, perform sentiment analysis, and predict Bitcoin prices, run the Jupyter notebooks in the following order:
1. `reddit_scrap.ipynb`
2. `bitcoin_sentiment.ipynb`
3. `prediction.ipynb`

Ensure you have the necessary data files in the appropriate directories.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
