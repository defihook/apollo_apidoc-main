---
type: apidoc
project: hmg
area: node
module: store-credit
owner: leanscale
reason: hmg-documentation
---


# Submit Store credit	
#cart #store-credit
- From: E Pharmarcy Frontend
- To: Node API
- Method: `PUT`
- API: `/api/V1/cart/store-credit`


## Response data extends to [response format](response_format.md)
```js
OK
```


# Delete Store credit	
#cart store-credit

- From: E Pharmarcy Frontend
- To: Node API
- Method: `DELETE`
- API: `/api/V1/cart/store-credit`

## Response data extends to [response format](response_format.md)
```js
OK
```

# Customer store credit history	
#customer #store-credit
-From: E Pharmacy Frontend
-To: Node API
-Method: `GET`
-API: `​/api​/V1​/customer​/store-credits-history`

## Response data extends to [response format](response_format.md)

```json
{
  "items": [
    {
      "action": "Created",
      "balance_change": {
        "value": 25,
        "currency": "SAR"
      },
      "actual_balance": {
        "value": 25,
        "currency": "SAR"
      },
      "date_time_changed": "2022-11-10 06:58:21"
    }
  ],
  "total_count": 1,
  "current_page": 1,
  "page_size": 20,
  "total_page": 1
}
```
# Customer store credit balance	
GET​/api​/V1​/customer​/store-credits
#customer #store-credit
-From: E Pharmacy Frontend
-To: Node API
-Method: `GET`
-API: `/api​/V1​/customer​/store-credits`

## Response data extends to [response format](response_format.md)

```json
{
  "value": 25,
  "currency": "SAR"
}
```