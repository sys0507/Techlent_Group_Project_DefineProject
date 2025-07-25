# Credit Risk Web Crawler and Dataset Enhancement

This project implements a sophisticated web crawler designed to enhance credit risk datasets with real-time market data about loan types and home ownership patterns. The crawler collects and processes information from reputable financial websites to generate risk scores for different loan intents and home ownership categories.

## Features

- **Intelligent Web Crawling**: Uses both requests and Selenium for robust data collection
- **Multi-source Data Collection**: Crawls multiple reputable financial websites for each loan type and home ownership category
- **Advanced Data Validation**: Implements comprehensive validation thresholds and confidence scoring
- **Historical Data Tracking**: Maintains and updates historical statistics for trend analysis
- **Parallel Processing**: Utilizes ThreadPoolExecutor for efficient URL processing
- **Robust Error Handling**: Implements retry logic and extensive error logging
- **Data Enhancement**: Adds new risk-related features to existing credit risk datasets

## Supported Loan Types

- Education Loans
- Medical Loans
- Venture/Business Loans
- Home Improvement Loans
- Debt Consolidation Loans
- Personal Loans

## Supported Home Ownership Categories

- Rent
- Mortgage
- Own

## Installation

1. Clone the repository
2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Basic Usage

```python
from real_web_crawler import LoanDataCrawler

# Initialize the crawler
crawler = LoanDataCrawler()

# Enhance an existing dataset
input_file = 'credit-risk-dataset/credit_risk_dataset.csv'
output_file = 'credit-risk-dataset/enhanced_credit_risk_dataset.csv'
enhanced_df = crawler.enhance_credit_risk_dataset(input_file, output_file)
```

### Output Features

The crawler adds the following new features to your dataset:

- `loan_intent_risk_score`: Risk score based on loan type
- `home_ownership_risk_score`: Risk score based on home ownership status
- `combined_risk_score`: Weighted combination of both risk scores

## Data Validation

The crawler implements the following validation thresholds:

- Default Rate: 0.1% - 30.0%
- Interest Rate: 2.0% - 35.0%
- Loan Amount: $1,000 - $500,000

## Historical Data Management

- Maintains 90 days of historical data
- Implements weighted averaging favoring recent data
- Calculates confidence scores for all metrics

## Error Handling and Logging

- Comprehensive logging system
- Automatic retry mechanism for failed requests
- User agent rotation
- Parallel processing with error recovery

## Files Generated

1. `crawled_data_raw.json`: Raw data collected from websites
2. `crawled_data_processed.json`: Processed risk scores
3. `historical_loan_data.json`: Historical loan statistics
4. `historical_stats.json`: Aggregated historical statistics
5. `web_crawler.log`: Detailed logging information

## Dependencies

- requests
- beautifulsoup4
- pandas
- numpy
- selenium
- fake-useragent
- webdriver_manager

## Best Practices

- Implements rate limiting and random delays between requests
- Uses dynamic user agent rotation
- Implements parallel processing with safety limits
- Maintains historical data for trend analysis
- Provides confidence scores for all metrics

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

This web crawler is designed for educational and research purposes. Always respect websites' robots.txt files and terms of service when deploying web crawlers in production environments.
