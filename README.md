# Google Ads API - Search Terms Reporting

A comprehensive Jupyter notebook for connecting to Google Ads API and generating detailed search terms reports with campaign performance metrics.

## 🚀 Features

- **OAuth 2.0 Authentication** with Google Ads API
- **Search Terms Reporting** with comprehensive metrics
- **Campaign Performance Overview**
- **Data Export** to CSV format
- **Manager Account (MCC) Support** - automatically detects and queries client accounts
- **Comprehensive Metrics** including:
  - Search terms and status (Added/Excluded)
  - Campaign and Ad Group details
  - Performance metrics (Impressions, Clicks, CTR, Cost, CPC)
  - Conversion data (Conversions, Conversion Value, Cost per Conversion)
  - Date-based reporting

## 📋 Prerequisites

### 1. Google Cloud Setup
- Google Cloud Project with Google Ads API enabled
- OAuth 2.0 client credentials (Desktop Application type)
- Approved Google Ads Developer Token

### 2. Python Environment
- Python 3.8+ 
- Conda environment (recommended: `CAB_V1_20250504`)

### 3. Required Libraries
```bash
# Install Google Ads Python client library
pip install git+https://github.com/googleads/google-ads-python.git

# Install additional dependencies
pip install google-auth-oauthlib gspread
```

## 🔧 Setup Instructions

### 1. OAuth Client Configuration
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Navigate to **APIs & Services** > **Credentials**
3. Create **OAuth 2.0 Client ID** (Desktop Application)
4. Download the JSON file and rename it to `client_secret.json`
5. Place it in the project directory

### 2. Environment Variables
Create a `.env` file with your credentials:
```env
GOOGLE_ADS_DEVELOPER_TOKEN=your_developer_token_here
GOOGLE_ADS_CUSTOMER_ID=your_customer_id_here
```

### 3. Google Ads API Setup
1. Enable Google Ads API in Google Cloud Console
2. Ensure your Developer Token is approved by Google
3. Verify your Customer ID has proper access permissions

## 📊 Usage

### Running the Notebook
1. Open `Google_Ads_API_Test.ipynb`
2. Run cells sequentially:
   - **Cell 1**: Environment Setup
   - **Cell 2**: OAuth Authentication (opens browser)
   - **Cell 3**: Test API Connection
   - **Cell 4**: Search Terms Reporting
   - **Cell 5**: Campaign Performance Overview
   - **Cell 6**: Export to Google Sheets (optional)
   - **Cell 7**: Export to CSV

### Sample Output
The notebook generates comprehensive reports including:
- **Search Terms**: Actual search queries with performance data
- **Campaign Details**: Campaign and Ad Group information
- **Performance Metrics**: Impressions, clicks, CTR, cost, conversions
- **Status Information**: Whether terms are added or excluded
- **Date-based Data**: Last 7 days performance

## 📈 Report Features

### Search Terms Report
- **Search Term**: The actual query users searched for
- **Status**: ADDED (in account) or NONE (not in account)
- **Campaign/Ad Group**: Associated campaign and ad group details
- **Performance**: Impressions, clicks, CTR, cost, CPC
- **Conversions**: Conversion count, value, and cost per conversion
- **Date**: When the data was recorded

### Summary Statistics
- Total search terms analyzed
- Overall performance metrics
- Status breakdown (Added vs. Not Added)
- Cost and conversion summaries

## 🔒 Security

This repository is configured to exclude sensitive files:
- `.env` files with credentials
- OAuth client secret JSON files
- Service account key files
- CSV exports with sensitive data

**Never commit credentials or API keys to version control!**

## 📁 File Structure

```
├── Google_Ads_API_Test.ipynb    # Main working notebook
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── .gitignore                   # Git ignore rules
└── client_secret.json          # OAuth credentials (not in git)
```

## 🛠️ Troubleshooting

### Common Issues

1. **"Service does not exist" Error**
   - Install the library from GitHub: `pip install git+https://github.com/googleads/google-ads-python.git`

2. **"Manager Account" Error**
   - The notebook automatically handles Manager Accounts (MCC)
   - It will query client accounts under the manager

3. **OAuth Authentication Issues**
   - Ensure OAuth client is configured as "Desktop Application"
   - Check redirect URIs in Google Cloud Console

4. **Permission Errors**
   - Verify Developer Token is approved
   - Check Customer ID access permissions
   - Ensure Google Ads API is enabled

### API Version Compatibility
- Uses Google Ads API v21 (latest supported version)
- Automatically falls back to compatible versions
- Handles deprecated version warnings

## 📚 Resources

- [Google Ads API Documentation](https://developers.google.com/google-ads/api/docs)
- [OAuth 2.0 Setup Guide](https://developers.google.com/google-ads/api/docs/client-libs/python/oauth-web)
- [Query Builder](https://developers.google.com/google-ads/api/fields/overview)
- [Python Client Library](https://developers.google.com/google-ads/api/docs/client-libs/python)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is for educational and business use. Please ensure compliance with Google Ads API Terms of Service.

## ⚠️ Disclaimer

This tool is provided as-is. Users are responsible for:
- Securing their API credentials
- Complying with Google Ads API terms
- Ensuring data privacy and security
- Proper usage of Google Ads data

---

**Happy Reporting! 📊**