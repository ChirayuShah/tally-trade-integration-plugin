# Tally Trade Integration Plugin

A TDL plugin for Tally ERP that integrates trade data into the Sales Voucher entry window and provides automatic prefilling of quantity and rate fields.

## Features

- Fetches trade data from JSON API
- Displays trades in Sales Voucher entry window
- Auto-prefills quantity and rate fields
- Modern UI with proper formatting
- Robust error handling and logging
- Automatic refresh of trade data
- Configurable settings

## Installation

1. Copy all .tdl files to your Tally TDL folder:
   - TradesPlugin.tdl
   - TradesConfig.tdl
   - TradesError.tdl
   - TradesJSON.tdl

2. Configure the API endpoint in TradesConfig.tdl:
   - Open TradesConfig.tdl
   - Update the API_ENDPOINT variable with your JSON API URL
   - Adjust other configuration variables as needed

3. Load the plugin in Tally:
   - Start Tally ERP
   - Press F1 (or go to Gateway of Tally > F1: Help)
   - Select TDL & Add-on
   - Load TradesPlugin.tdl

## Usage

1. Open a Sales Voucher entry screen
2. The trade panel will appear showing available trades
3. Click on any trade to auto-fill:
   - Scrip Name
   - Quantity
   - Rate

## Error Handling

The plugin includes comprehensive error handling:
- API connection issues
- JSON parsing errors
- Data validation
- Automatic retry mechanism

Logs are stored in: TallyLogs/trades_plugin.log

## Configuration Options

Edit TradesConfig.tdl to customize:
- API endpoint URL
- Refresh interval
- UI appearance
- Logging settings
- Timeout values

## Troubleshooting

1. If trades are not displaying:
   - Check API endpoint configuration
   - Verify network connectivity
   - Check error logs

2. If auto-fill is not working:
   - Ensure trade data format is correct
   - Check for any error messages
   - Verify field mappings

3. For connection issues:
   - Check network connectivity
   - Verify API endpoint is accessible
   - Check timeout settings

## Support

For support or bug reports, please contact your system administrator or Tally support team.

## Technical Details

### API Response Format
The plugin expects JSON data in the following format:
```json
{
  "trades": [
    {
      "scrip": "EXAMPLE",
      "qty": 100,
      "rate": 50.25
    }
  ]
}
```

### System Requirements
- Tally ERP Release 6.0 or higher
- Network connectivity for API access
- Minimum 4GB RAM recommended

### Performance Considerations
- Trade data refreshes every 5 minutes by default
- Logs are automatically rotated to prevent disk space issues
- Timeout values can be adjusted for slower networks
