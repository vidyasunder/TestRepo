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
