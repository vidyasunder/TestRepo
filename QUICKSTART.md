# Getting Started with Nearmap APIs

Welcome! This guide helps you make your first API call.

## Prerequisites
- Valid Nearmap API key
- Your location coordinates (latitude/longitude)

## 1. Get Your API Key
Visit your account settings to retrieve your API key.

## 2. Make Your First Request
```bash
curl "https://api.nearmap.com/coverage/point/40.7128,-74.0060?apikey=YOUR_API_KEY"
```

## 3. Parse the Response
The response includes available survey resources at that location.

## Next Steps
- [Coverage API Documentation](../docs/coverage)
- [Authentication Guide](../docs/authentication)

## Example: Using Python
Here's a quick Python example to query the Coverage API:

```python
import requests

API_KEY = "your_api_key_here"
POINT = "40.7128,-74.0060"

url = f"https://api.nearmap.com/coverage/point/{POINT}"
params = {"apikey": API_KEY}

response = requests.get(url, params=params)
data = response.json()

print(f"Found {len(data['resources'])} resources at this location")
```
