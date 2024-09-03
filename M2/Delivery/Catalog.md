---
type: apidoc
project: hmg
area: magento
owner: leanscale
module: catalog
reason: hmg-documentation
---

# Get product attributes list
#cart

- From: Node API
- To: M2
- Method: `GET`
- API: `/rest/alhabib_en/V1/products/attributes`
### The response is returned according to which store_view is sent.
```raw
{
    "items": [{
        "is_wysiwyg_enabled": false,
        "is_html_allowed_on_front": false,
        "used_for_sort_by": true,
        "is_filterable": false,
        "is_filterable_in_search": false,
        "is_used_in_grid": false,
        "is_visible_in_grid": false,
        "is_filterable_in_grid": false,
        "position": 0,
        "apply_to": [],
        "is_searchable": "1",
        "is_visible_in_advanced_search": "1",
        "is_comparable": "0",
        "is_used_for_promo_rules": "0",
        "is_visible_on_front": "0",
        "used_in_product_listing": "1",
        "is_visible": true,
        "scope": "store",
        "attribute_id": 73,
        "attribute_code": "name",
        "frontend_input": "text",
        "entity_type_id": "4",
        "is_required": true,
        "options": [],
        "is_user_defined": false,
        "default_frontend_label": "Product Name",
        "frontend_labels": [],
        "backend_type": "varchar",
        "is_unique": "0",
        "frontend_class": "validate-length maximum-length-255",
        "validation_rules": []
    }],
    "search_criteria": {
        "filter_groups": [],
        "page_size": 1
    },
    "total_count": 98
}
```

# Get product attributes list for all store views
#cart

- From: Node API
- To: M2
- Method: `GET`
- API: `/rest/V1/products/attributes/all`

## Response data extends to [response format](./response_format.md)

```raw
[{
    "store_id": 1,
    "store_view": "alhabib_ar",
    "product_attributes": {
        "items": [{
            "is_wysiwyg_enabled": false,
            "is_html_allowed_on_front": false,
            "used_for_sort_by": true,
            "is_filterable": false,
            "is_filterable_in_search": false,
            "is_used_in_grid": false,
            "is_visible_in_grid": false,
            "is_filterable_in_grid": false,
            "position": 0,
            "apply_to": [],
            "is_searchable": "1",
            "is_visible_in_advanced_search": "1",
            "is_comparable": "0",
            "is_used_for_promo_rules": "0",
            "is_visible_on_front": "0",
            "used_in_product_listing": "1",
            "is_visible": true,
            "scope": "store",
            "attribute_id": 73,
            "attribute_code": "name",
            "frontend_input": "text",
            "entity_type_id": "4",
            "is_required": true,
            "options": [],
            "is_user_defined": false,
            "default_frontend_label": "Product Name",
            "frontend_labels": [],
            "backend_type": "varchar",
            "is_unique": "0",
            "frontend_class": "validate-length maximum-length-255",
            "validation_rules": []
        }],
        "search_criteria": {
            "filter_groups": [],
            "page_size": 1
        },
        "total_count": 98
    }
}, {
    "store_id": 2,
    "store_view": "alhabib_en",
    "product_attributes": {
        "items": [{
            "is_wysiwyg_enabled": false,
            "is_html_allowed_on_front": false,
            "used_for_sort_by": true,
            "is_filterable": false,
            "is_filterable_in_search": false,
            "is_used_in_grid": false,
            "is_visible_in_grid": false,
            "is_filterable_in_grid": false,
            "position": 0,
            "apply_to": [],
            "is_searchable": "1",
            "is_visible_in_advanced_search": "1",
            "is_comparable": "0",
            "is_used_for_promo_rules": "0",
            "is_visible_on_front": "0",
            "used_in_product_listing": "1",
            "is_visible": true,
            "scope": "store",
            "attribute_id": 73,
            "attribute_code": "name",
            "frontend_input": "text",
            "entity_type_id": "4",
            "is_required": true,
            "options": [],
            "is_user_defined": false,
            "default_frontend_label": "Product Name",
            "frontend_labels": [],
            "backend_type": "varchar",
            "is_unique": "0",
            "frontend_class": "validate-length maximum-length-255",
            "validation_rules": []
        }],
        "search_criteria": {
            "filter_groups": [],
            "page_size": 1
        },
        "total_count": 98
    }
}]
```
