# XRPL DEX API Documentation

This API documentation provides an overview of available endpoints for accessing decentralized exchange data and tools on the XRPL (XRP Ledger). The API provides real-time data on assets, pairs, events, and other XRPL-based metrics.

## API Base URLs

- **DEX Data API**: `https://dex.xrpldata.net`
- **DEX Tools API**: `https://tools.xrpldata.net`

## Endpoints

### 1. Get Latest Block
- **Endpoint**: `/latest-block`
- **Description**: Returns the latest validated block number and timestamp.
- **Method**: `GET`
- **Example**: `https://dex.xrpldata.net/latest-block` or `https://tools.xrpldata.net/latest-block`

### 2. Get Specific Block
- **Endpoint**: `/block`
- **Description**: Retrieves data for a specific block by block number.
- **Method**: `GET`
- **Parameters**:
  - `number` (required): Block number to fetch.
- **Example**: `https://tools.xrpldata.net/block?number=32570`

### 3. Get Asset Information
- **Endpoint**: `/asset`
- **Description**: Fetches details of specific assets on the XRPL.
- **Method**: `GET`
- **Parameters**:
  - `id` (required): Asset ID(s) to fetch, either a single ID or comma-separated IDs. Use the format `currency.issuer` for non-XRP assets.
- **Example**: `https://dex.xrpldata.net/asset?id=XRP`

### 4. Get Exchange Information
- **Endpoint**: `/exchange`
- **Description**: Provides metadata for specific exchanges.
- **Method**: `GET`
- **Parameters**:
  - `id` (required): Exchange ID.
- **Example**: `https://tools.xrpldata.net/exchange?id=74920348`

### 5. Get Pair Information
- **Endpoint**: `/pair`
- **Description**: Retrieves data for a given asset pair.
- **Method**: `GET`
- **Parameters**:
  - `id` (required): Pair ID in the format `base_quote`, where each asset is represented as `currency.issuer`.
- **Example**: `https://dex.xrpldata.net/pair?id=XRP_USD`

### 6. Get Events by Block Range
- **Endpoint**: `/events`
- **Description**: Fetches DEX events within a specified block range.
- **Method**: `GET`
- **Parameters**:
  - `fromBlock` (required): Starting block number.
  - `toBlock` (required): Ending block number.
- **Example**: `https://dex.xrpldata.net/events?fromBlock=10000&toBlock=10100`

---

## Rate Limits & Support

Each IP is limited to 120 requests per minute to ensure fair usage.

The API comes with NO support.

---

## Error Handling

Each endpoint will return standard HTTP errors if required parameters are missing or an error occurs while processing the request. Errors are returned in JSON format, typically structured as:
```json
{
  "code": <errorCode>,
  "message": "<error message>"
}
