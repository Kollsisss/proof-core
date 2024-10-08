# API Documentation

1. Introduction
This guide describes the API endpoints for interacting with the XYZ Blockchain.

2. Authentication
[Description of the authentication method, e.g., JWT tokens]

3. Endpoints

##  Get Account Information

```bash
GET /api/v1/account/{address}
```

## Parameters:

    address: Account address (string, required)

## Response:

```json
{
  "address": "0x1234...",
  "balance": "100.5",
  "nonce": 5
}
```

## Send Transaction

```bash
POST /api/v1/transaction
```

## Request Body:

```json
{
  "from": "0x1234...",
  "to": "0x5678...",
  "value": "10.5",
  "gas": 21000
}
```

## Response:
e
```json
{
  "transactionHash": "0xabcd...",
  "status": "pending"
}
```

4. Usage Examples

##  JavaScript (Node.js)

```js
const axios = require('axios');

async function getAccountInfo(address) {
  try {
    const response = await axios.get(`https://api.xyzblockchain.com/v1/account/${address}`);
    console.log(response.data);
  } catch (error) {
    console.error('Error:', error.message);
  }
}

getAccountInfo('0x1234...');
```

## Python

```py
import requests

def send_transaction(from_address, to_address, value):
    url = "https://api.xyzblockchain.com/v1/transaction"
    payload = {
        "from": from_address,
        "to": to_address,
        "value": value,
        "gas": 21000
    }
    response = requests.post(url, json=payload)
    print(response.json())

send_transaction("0x1234...", "0x5678...", "10.5")
```