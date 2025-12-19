# Financial Data & News Collection Pipeline

This repository contains a comprehensive data collection pipeline designed to aggregate historical stock market data and financial news for sentiment analysis and machine learning applications.

The notebook integrates multiple APIs to fetch quantitative market data (price/volume) and qualitative news data (headlines/summaries) for major tech stocks, covering the period from **January 2023 to December 2024**.

## 🚀 Features

* **Multi-Source Data Aggregation**:
* **Yahoo Finance (`yfinance`)**: Retrieves daily historical price data (Open, High, Low, Close, Volume).
* **Alpha Vantage**: Fetches news sentiment and historical articles.
* **Finnhub**: Retrieves company-specific news releases.
* **Google News (`gnews`)**: Scrapes historical news with advanced filtering.


* **Smart Noise Filtering**: Implements a custom "Blacklist" logic to filter out irrelevant news (e.g., removing cooking recipes for "Apple" or rainforest articles for "Amazon").
* **Rate Limit Handling**: Includes built-in pauses and batching to respect API rate limits.
* **Google Drive Integration**: Automatically saves and structures data directly to Google Drive.

## 🛠️ Supported Tickers

The pipeline is currently configured to process the following tech giants:

* **AAPL** (Apple Inc.)
* **AMZN** (Amazon.com Inc.)
* **GOOGL** (Alphabet Inc.)
* **META** (Meta Platforms Inc.)
* **MSFT** (Microsoft Corp.)

## 📋 Prerequisites

This project is designed to run in a Jupyter Notebook environment (specifically optimized for Google Colab).

### Required Libraries

```bash
pip install yfinance alpha_vantage finnhub-python gnews pandas transformers torch

```

### API Keys

To run this pipeline successfully, you will need API keys for the following services:

1. **Alpha Vantage**
2. **Finnhub**

*Note: Replace the placeholder keys in the code with your own valid API credentials.*

## 📂 Project Structure & Output

The script generates the following datasets saved as `.csv` files:

1. **Market Data**:
* Filename: `{TICKER}_stock_data.csv`
* Columns: `Date`, `Open`, `High`, `Low`, `Close`, `Volume`


2. **News Data**:
* Filename: `{TICKER}_GNews_2023_2024.csv` (and variants for other APIs)
* Columns: `Date`, `Title`, `Summary`, `Source`, `URL`, `Sentiment_Score` (where available)



## ⚙️ Usage

1. **Mount Drive**: The notebook will request access to mount Google Drive to save the collected datasets (`/content/drive/MyDrive/StockData`).
2. **Configure Keys**: Enter your API keys in the designated configuration cells.
3. **Run Pipeline**: Execute the cells sequentially. The `GNews` section allows for batch processing of all target tickers with long sleep intervals to prevent IP blocking.

## ⚠️ Disclaimer

This code is for educational and research purposes only. Stock market data and news availability are subject to the terms of service of the respective API providers.

---

**License**
MIT
