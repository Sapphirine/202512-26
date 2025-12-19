# Financial Sentiment and Market Correlation Analysis

EECS E6893: Big Data Analytics Final Project

This repo include:

- A dashboard comparing univariate Technical Analysis vs. multivariate Sentiment Analysis for stock price prediction using LSTM models.

## Features

- **Base Model**: LSTM using OHLCV features only
- **Advanced Model**: LSTM incorporating sentiment analysis
- **Interactive Dashboard**: Real-time visualization with date filtering
- **Model Comparison**: Side-by-side accuracy metrics

## Prerequisites

- Node.js
- Python 3.10+
- uv (recommended) or pip

## Quick Start

### 1. Install Dependencies

**Frontend:**
```bash
npm install
```

**Python:**
```bash
uv sync
# or
pip install -r requirements.txt
```

### 2. Download Stock Data

```bash
python scripts/data_acquisition.py
```

Downloads data for META, AAPL, MSFT, AMZN, GOOGL (2023-2024) to `data/` folder.

### 3. Train Models

**Base Model:**
```bash
python scripts/base_model.py
```

**Advanced Model:**
```bash
python scripts/advanced_model.py
```

### 4. Run Dashboard

```bash
npm run dev
```

Open `http://localhost:3000`

## Project Structure

```
├── data/              # Stock data CSV files
├── output/            # Model predictions and metrics
├── scripts/           # Python training scripts
├── components/        # React components
└── App.tsx           # Main application
```

## Usage

1. Select a ticker (META, AAPL, MSFT, AMZN, GOOGL)
2. View metrics and predictions
3. Filter by date range
4. Compare base vs advanced model performance

## Technologies

- **Frontend**: React, TypeScript, Vite, Recharts, Tailwind CSS
- **Backend/ML**: Python, TensorFlow/Keras, pandas, yfinance
