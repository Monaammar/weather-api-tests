# OpenWeatherMap API Tests (Postman)

API test collection for the OpenWeatherMap **Current Weather** endpoint.

## Test Scenarios

| Request | Type | Expected | Assertions |
|---|---|---|---|
| GET Current Weather - Cairo | Positive | 200 OK | 9 |
| GET Weather - Invalid City | Negative | 404 Not Found | 5 |
| GET Weather - Unauthorized (invalid API key) | Negative | 401 Unauthorized | 5 |

**Total: 19 assertions** covering status codes, response time, response format, schema (required fields), data types, realistic value ranges, and error messages.

## How to Run

1. Import both JSON files from this folder into Postman.
2. Get a free API key from https://openweathermap.org/api
3. Open the `OpenWeather` environment and paste your key into `apiKey`.
4. Select the `OpenWeather` environment (top-right), then **Run** the collection.

> The API key is intentionally not committed. It is stored as an environment variable (`{{apiKey}}`) and never hard-coded in requests.

## Observation

The `cod` field is returned as a **string** (`"404"`) for an invalid city but as a **number** (`401`) for an invalid API key — an inconsistency in the API's error response format.
