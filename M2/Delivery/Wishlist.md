---
type: apidoc
project: hmg
area: magento
owner: leanscale
module: wishlist
reason: hmg-documentation
---


# View wishlist
#wishlist

- From: Node API
- To: M2
- Method: `GET`
- API: `/api/V1/wishlist`

## Response data extends to [response format](response_format.md)

```json
{
    "wishlist_id": 2,
    "customer_id": 18,
    "sharing_code": "3LNPqsz7pofymxMYlPK5tOci9n45HJVx",
    "items_count": 1,
    "items": [{
        "id": 1,
        "qty": 2,
        "added_at": "2022-10-27 23:55:05",
        "product_id": int,
    }]
}
```

# Add products to wishlist
#wishlist

- From: Node API
- To: M2
- Method: `PUT`
- API: `/api/V1/wishlist/{product_id}`

## Response data extends to [response format](response_format.md)
```
true|false
```

# Delete products from wishlist
#wishlist

- From: Node API
- To: M2
- Method: `DELETE`
- API: `/api/V1/wishlist/{item_id}`


## Response data extends to [response format](response_format.md)
```json
true|false
```

# Add item to cart [POSTMVLP]
#wishlist

- From: Node API
- To: M2
- Method: `POST`
- API: `/api/V1/wishlist/cart/{item_id}`

## Response data extends to [response format](response_format.md)
```json
true|false
```