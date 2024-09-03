---
type: apidoc
project: hmg
area: magento
owner: leanscale
module: search
reason: hmg-documentation
---


# Get search query
#search

- From: Node API
- To: M2
- Method: `GET`
- API: `/api/V1/alhabib/search/query`

## Request
### Params
- requestName: `catalog_view_container`, `category_search_container`, `pharmacy_view_container`, `quick_search_container`, `catalog_product_autocomplete`
- condition_type: eq, neq, like, nlike, is, in, nin, lt, lteq, gt, gteq, finset, null, notnull
```
searchCriteria[requestName]=catalog_view_container&searchCriteria[filter_groups][0][filters][0][field]=name&searchCriteria[filter_groups][0][filters][0][value]=Poison&searchCriteria[filter_groups][0][filters][0][condition_type]=like
```

## Response data extends to [response format](response_format.md)

```json
{"size":20,"sort":[{"category.position":{"order":"asc","missing":"_last","unmapped_type":"keyword","nested":{"path":"category","filter":{"terms":{"category.category_id":["2"],"boost":1}}},"mode":"min"}},{"_score":{"order":"desc"}},{"entity_id":{"order":"desc","missing":"_first","unmapped_type":"keyword"}}],"from":0,"query":{"constant_score":{"filter":{"bool":{"must":[{"term":{"stock.is_in_stock":{"value":true,"boost":1}}},{"terms":{"visibility":[2,4],"boost":1}},{"bool":{"must_not":[{"nested":{"path":"category","score_mode":"none","query":{"bool":{"must":[{"term":{"category.category_id":{"value":2,"boost":1}}},{"term":{"category.is_blacklisted":{"value":true,"boost":1}}}],"must_not":[],"should":[],"boost":1}},"boost":1}}],"boost":1}},{"match":{"name.standard":{"query":"Poison","minimum_should_match":"100%","boost":1}}}],"must_not":[],"should":[],"boost":1}},"boost":1}},"aggregations":{"attribute_set_id":{"terms":{"field":"attribute_set_id","size":100000,"order":{"_count":"desc"}}},"indexed_attributes":{"terms":{"field":"indexed_attributes","size":100000,"order":{"_count":"desc"}}},"categories":{"filters":{"filters":{"3":{"nested":{"path":"category","score_mode":"none","query":{"bool":{"must":[{"bool":{"must_not":[{"term":{"category.is_virtual":{"value":true,"boost":1}}}],"boost":1}},{"terms":{"category.category_id":["3"],"boost":1}}],"must_not":[],"should":[],"boost":1}},"boost":1}},"5":{"nested":{"path":"category","score_mode":"none","query":{"bool":{"must":[{"bool":{"must_not":[{"term":{"category.is_virtual":{"value":true,"boost":1}}}],"boost":1}},{"terms":{"category.category_id":["5"],"boost":1}}],"must_not":[],"should":[],"boost":1}},"boost":1}}}}}},"track_total_hits":true}
```

# Get search result
#search

- From: Node API
- To: M2
- Method: `GET`
- API: `/api/V1/alhabib/search`

## Request
```
searchCriteria[requestName]=catalog_view_container&searchCriteria[filter_groups][0][filters][0][field]=name&searchCriteria[filter_groups][0][filters][0][value]=Poison&searchCriteria[filter_groups][0][filters][0][condition_type]=like
```

## Response data extends to [response format](response_format.md)

```json
{"items":[],"aggregations":{"buckets":[{"name":"indexed_attributes","values":[]},{"name":"attribute_set_id","values":[]},{"name":"categories","values":[{"value":"3","metrics":[0]},{"value":"5","metrics":[0]}]}],"bucket_names":["indexed_attributes","attribute_set_id","categories"]},"search_criteria":{"request_name":"catalog_view_container","filter_groups":[{"filters":[{"field":"name","value":"Poison","condition_type":"like"}]}]},"total_count":0}
```
