---
type: apidoc
project: hmg
area: node
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

```js
{
    "wishlist_id": 2,
    "customer_id": 18,
    "sharing_code": "3LNPqsz7pofymxMYlPK5tOci9n45HJVx",
    "items_count": 1,
    "items": [{
        "id": 1,
        "qty": 2,
        "added_at": "2022-10-27 23:55:05",
        "product": {
			product.id,
			product.type,
			product.sku,
			product.name,
			product.status,
			product.media,
			product.price,
			product.original_price?,
			product.lakum?,
			product.labels?
		}
    }]
}
```

### Example elastic query for wishlist item response
```json
{
  "_source": {
    "includes": [
        "id",
        "type",
        "sku",
        "name",
        "status",
        "media",
        "price",
        "original_price",
        "lakum",
        "labels"
    ]
  },
  "query": {
    "bool": {
      "must": [
        {
          "term": {
            "entity_id": "12"
          }
        }
      ],
      "must_not": [],
      "should": []
    }
  },
  "from": 0,
  "size": 10,
  "sort": [],
  "aggs": {}
}
```

# Add products to wishlist
#wishlist

- From: Node API
- To: M2
- Method: `POST`
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
- API: `/api/V1/wishlist/{product_id}`


## Response data extends to [response format](response_format.md)
```json
true|false
```