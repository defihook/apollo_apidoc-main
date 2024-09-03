---
type: apidoc
project: hmg
area: magento
module: store-credit
owner: leanscale
reason: hmg-documentation
---

# Get Store Credit

- From: Node
- To: M2
- Method: `GET`
- API:
 - `/V1/customers/balance/me` with customer token
 - `/V1/customers/balance/{customerId}` with admin token

## Response data extends to [response format](./response_format.md)
```json
{
  "value": 100,
  "currency": "SAR"
}
```

# Get Store Credit History

- From: Node
- To: M2
- Method: `GET`
- API:
 - `/V1/customers/balance/history/me` with customer token
 - `/V1/customers/balance/history/{customerId}` with admin token

## Request (optional)
```json
{
    "page_size": 20,
    "current_page": 1
}
```

## Response data extends to [response format](./response_format.md)
```json
{
    "items": [{
        "action": "Updated",
        "balance_change": {
            "value": 1000,
            "currency": "SAR"
        },
        "actual_balance": {
            "value": 1000,
            "currency": "SAR"
        },
        "date_time_changed": "2022-11-13 14:01:40"
    }],
    "total_count": 1,
    "current_page": 1,
    "page_size": 20,
    "total_page": 1
}
```

# Apply Store Credit to Cart
#cart

- From: Node
- To: M2
- Method: `POST`
- API: `/V1/carts/mine/balance/apply` with customer token

## Response data extends to [response format](./response_format.md)
```json
{cartResponse}
```

# Unapply Store Credit to Cart
#cart

- From: Node
- To: M2
- Method: `POST`
- API: `/V1/carts/mine/balance/unapply` with customer token

## Response data extends to [response format](./response_format.md)
```json
{cartResponse}
```
