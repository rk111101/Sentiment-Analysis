# Bitcoin News Sentiment Analysis and Price Impact Project

## Overview
This project analyzes the impact of news sentiment on Bitcoin price movements using data from Binance. It employs sentiment analysis on news articles to predict price changes and evaluates two trading strategies: **Look-Ahead Bias** and **Slow Reaction**. The project includes data retrieval, sentiment analysis, statistical testing, and trading simulations to assess the effectiveness of sentiment-driven trading decisions.

### Key Features
- **Data Collection**: News articles are loaded from a CSV file (`bitcoin news.csv`), and Bitcoin price data is retrieved from Binance.
- **Sentiment Analysis**: Uses VADER to compute sentiment scores for news summaries.
- **Price Movement Analysis**: Computes returns for 1-day, 7-day, and trade closure periods based on news events.
- **Statistical Analysis**: Includes descriptive statistics, Pearson and point-biserial correlations, T-tests, and ANOVA.
- **Trading Simulation**: Simulates trading strategies with transaction fees and tracks portfolio performance.
- **Visualizations**: Plots Bitcoin price with sentiment markers and portfolio value over time.

## Installation
To run this project, you need Python 3.8+ and the following libraries:

```bash
pip install pandas numpy requests binance scipy scikit-learn statsmodels matplotlib vaderSentiment
```

### Additional Requirements
- **Binance API**: Used for retrieving Bitcoin price data. No API key is required as the `Spot` client is used for public data.
- **News Data**: A CSV file (`bitcoin news.csv`) containing news summaries and publication dates in the format: `date`, `time`, `summary`.

## Usage
1. **Prepare News Data**: Ensure the `bitcoin news.csv` file is in the project directory with the correct format:
   - Columns: `date` (YYYY-MM-DD), `time` (HH:MM:SS), `summary` (text).
   - Example:
     ```csv
     date,time,summary
     2021-01-29,07:00:00,"Elon Musk changes his X bio to “#bitcoin,” prompting posts like “Is Tesla buying BTC? Price about to moon!” on X."
     ```

2. **Update File Path**: Modify the `csv_path` in the `main()` function of `FTEC4008 code submission.ipynb` to point to your `bitcoin news.csv` file:
   ```python
   csv_path = r"path/to/your/bitcoin news.csv"
   ```

3. **Run the Script**: Execute the Jupyter Notebook or convert it to a Python script:
   - Using Jupyter Notebook:
     ```bash
     jupyter notebook "FTEC4008 code submission.ipynb"
     ```
     Then run all cells.
   - As a Python script:
     ```bash
     python trading_analysis_with_statistics.py
     ```
   *Note*: If running as a script, ensure the code is adapted to run outside Jupyter (e.g., remove `display()` calls).

4. **Output**:
   - **Console**: Displays completed and ongoing trades for both strategies, statistical analysis results.
   - **Files**: Saves a plot (`bitcoin_sentiment_with_news_table.png`) showing Bitcoin price with sentiment markers and a news table.

## Data Sources
- **News Data**: Curated news summaries from various sources, stored in `bitcoin news.csv`.
- **Price Data**: Hourly Bitcoin price data from Binance, retrieved via the `binance.spot.Spot` client.

## Project Structure
- **FTEC4008 code submission.ipynb**: Main Jupyter Notebook containing all code.
- **bitcoin news.csv**: Input data file with news events.
- **Data Loading**: Functions to load news (`load_news_from_csv`) and price data (`retrieve_data_from_binance`).
- **Sentiment Analysis**: Functions to compute sentiment (`analyze_sentiment`, `process_news_sentiment`).
- **Price Movement Analysis**: Function to analyze returns (`analyze_price_movements`).
- **Visualizations**: Function to plot data (`plot_sentiment_with_news`).

## Execution Instructions
1. **Set Up Environment**:
   - Install Python 3.8+.
   - Install required libraries using the `pip` command above.

2. **Prepare Data**:
   - Place the `bitcoin news.csv` file in the same directory as the notebook or update the `csv_path` accordingly.

3. **Run the Main Function**:
   - Open the notebook in Jupyter and execute all cells, or run the converted script.
   - The `main()` function orchestrates data loading, sentiment analysis, price retrieval, and visualization.

4. **Review Outputs**:
   - Check the console for analysis results (trades, statistics).
   - Open `bitcoin_sentiment_with_news_table.png` to view the visualization.

## Challenges and Future Work
- **Data Limitations**: Limited neutral sentiment events; future work could include more diverse news sources.
- **Model Enhancements**: Explore non-linear models or machine learning to improve sentiment-return predictions.
- **Risk Management**: Implement advanced risk controls like stop-losses and position sizing.

## Conclusion
The project demonstrates that news sentiment significantly impacts Bitcoin price movements, with the Slow Reaction strategy offering practical trading opportunities. The analysis provides insights into sentiment-driven trading and suggests refinements for real-world application.
