---
type: apidoc
project: hmg
area: node
module: catalog
owner: leanscale
reason: hmg-documentation
---


# List all categories
#category
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/categories`

## Response data extends to [response format](response_format.md)
```json
[
	{
		"id": number,
		"parent_id": number,
		"name": "string",
		"image": "string",
		"code": "string",
		"is_active": true,
		"position": 1,
		"level": 1,
		"product_count": number,
		"is_featured": false,
		"display_name": "string",
		"url_key": "",
		"meta_title": "string",
		"meta_keywords": "string",
		"meta_description": "string",
		"include_in_menu": true,
		"category_event_reporting": "string",
		"children_data": [
			{
				"id": number,
				"parent_id": number,
				"name": "string",
				"image": "string",
				"code": "string",
				"is_active": true,
				"position": 1,
				"level": 1,
				"product_count": number,
				"children_data": [],
				"is_featured": false,
				"display_name": "string",
				"url_key": "",
				"meta_title": "string",
				"meta_keywords": "string",
				"meta_description": "string",
				"include_in_menu": true,
				"category_event_reporting": "string",
			}	
		],
	}
]
```


# Get Content of a Category
#category #cms #catalog #filter
Returns description of any category with any [value type](CMS.md). 

Creating Product filters
- Get `product_filters` of a Category from Elastic
- Iterate the filter after Applying it with Aggregations from Elastic Query result and show selected while returning the response.
- Pull all Attributes at once and save it to the cache from [here](../M2/Delivery/Catalog.md)


- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/categories/{id}`

## Response data extends to [response format](response_format.md)
```js
{
	content: ...contentTypesFromHtmlToJson, // full_banner, single_banner, slider, category_grid, category_slider
	product_filters: {
		display_price: {
			min: () => getCheaper(),
			max: () => getMax()
		},
		category: {
	    options: [
	      {
	        value: 1,
	        label: "Health Care",
					amount: 34,
	      }, 
	      {
	        value: 2,
	        key: "ABC Cate",
					amount: 34,
	      }
	    ]
		},
		color?: {
	    label: "Color",
	    options: [
	      {
	        value: 1,
	        label: "Black",
					amount: 34,

	      }, 
	      {
	        value: 2,
	        key: "White",
					amount: 34,
	      }
	    ]
	  },
	},
	products: [
		...getProductsFromACategoryResponse
	] 
}
```


# Filter Apply
#category #catalog #filter

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/catalog/​filter​/apply`

### Request body
```js
{
  keyword?: "string",
  category: [...selectedCategoryIds],
  display_price: {min, max},
  good_for: 1,
	attribute: value
}
```

### Response data extends to [response format](response_format.md) for Example Product feed from Elastic given above.
```js
{
	product_filters: {
	  keyword?: "string",
	  category: {
			options: [
	      {
	        value: 1,
	        label: "Health Care",
	        selected: true,
	      }, 
	      {
	        value: 2,
	        key: "ABC Cate",
	        selected: false,
	      }
	    ]
		},
	  display_price: {
	      min,
	      max,
	  }
	  good_for?: {
	    label: "Good For",
	    options: [
	      {
	        value: 1,
	        label: "Heart conditions",
	        selected: true,
	      }, 
	      {
	        value: 2,
	        key: "Muscle Functions",
	        selected: false,
	      }
	    ]
	  },
	  test_attr?: {
	    label: "Test Attribute",
	    options: [
	      {
	        value: 12,
	        key: "test_attr_1",
	        selected: false,
	      },
	      {
	        value: 13,
	        key: "test_attr_2",
	        selected: false,
	      },
	      {
	        value: 14,
	        key: "test_attr_3",
	        selected: false,
	      },
	    ]
	  },
	},
	products: [
		...filteredProductResult
	]
}
```

# Get Products of a category
#category
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/categories/{id}/products`

## Response data extends to [response format](response_format.md)
```json
[
	{
		...product
	},
	...products
]
```



# Get reviews for a product
#product
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/product/{SKU}/reviews`

## Response data extends to [response format](response_format.md)
```json
{
	"total_count": number,
	"reviews": [
		{
		  "review_id": "string",
		  "created_at": "string",
		  "title": "string",
		  "detail": "string",
		  "nickname": "abc",
		  "vote": "4"
		}
	]
},
```

# Add a review for a product
#product
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/product/{SKU}/reviews`

## Request 
```json
{
  "vote": number,
  "name": "string",
  "title": "string",
  "detail": "string"
}
```

# Search in products.
#product
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/products/search`

Search {keyword} |>
	1. Product name %50
	2. Product description %30
	3. Category Name %15
	4. Rest of the product attributes %5

# Get product information. 
#product
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/catalog/products/{sku}`


## Response data extends to [response format](response_format.md)

### Simple product
```js
{
	"entity_id": "string",
	"type": "simple" // simple, configurable [to be added later on: virtual, gift-card, bundle, group]
	"sku": "string",
	"price": { // Optional when there is no stock
		"price": float,
		"price_rounded": number,
		"tax": number,
		"with_tax": number,
		"with_tax_rounded": number,
	},
	"original_price": { // Optional
		"price": float,
		"price_rounded": number,
		"tax": number,
		"with_tax": number,
		"with_tax_rounded": number,
	},
	"category": [
		{
			"category_id": 3,
			"name": "Gear"
		},
		{
			"category_id": 5,
			"name": "Personal Care"
		}
	],
	"name": "string",
	"visibility": "int",
	"status": "string", // in-stock, pre-order, prescription, disabled
	"is_pickup_available": boolean,
	"spf": "string",
	"composition": "string",
	"storage": "string",
	"brand": "string",
	"rx": boolean,
	"media": {
		"image": [
			{
				"original": "assetUrl",
				"position": number,
				"id": int,
				"alt_text": "string"
				"width": "string",
				"height": "string",
				"type": ["image"] // image || small_image || thumbnail || swatch_image
			}
		]
		"video": [
			{
				"original": "https://m2-alpha.alhabibpharmacydev.com/media/alhabib/pharmacy/6/8/681023231-da34e34f89db49761936903f8e7564c151794a696433a6f6214620a9802f3d0c-d_640",
				"id": 2,
				"position": 2,
				"video_url": "https://vimeo.com/253989945",
				"video_title": "Sample Videost",
				"type": ["image"] // image || small_image || thumbnail || swatch_image
			}
		]
	},
	"currency": "SAR"
	
	"lakum": {
	    "points": number, // price.price * 1 
	    "money_equivalent": number // points * 0.05 
	},
	"labels": { // POST MVLP
		"plp": [
			{
			"type": "text",
			"text": "string",
			"position": "string"
			/**
				| ----------- | ------ | ------------ |
				| top_left    | top    | top_right    |
				| ----------- | ------ | ------------ |
				| left        | middle | right        |
				| ----------- | ------ | ------------ |
				| bottom_left | bottom | bottom_right |
				| ----------- | ------ | ------------ |
			
			**/
			}
		],
		"pdp": [
			{
			"type": "image",
			"image": "string",
			"position": "center_bottom"
			}
		]
	},
	
	"stock": [
		{
			"sub_inventory_code": "string",
			"organization_name": "string",
			"stock": "int",
			"is_in_stock": "bool"
		}
	],

	"attributes": { // here, remaining product attributes comes dynamically
		"attribute_code": { // unique identifier of the attribute
			"label": "string", // attribute label
			"visible": true,
			"options": [{value, label}] // conditional if the type is one of "select", "boolean", "multiselect", "swatch_visual", "swatch_text"
			"filterable": false,
			"type": "select" // Other available types: boolean, multiselect, swatch_visual, swatch_text, text, textarea, texteditor, date, datetime, price, media_image, wee
		},
	},
	"related_products": [
	  {
			product.entity_id,
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
	],
	"upsell_products": [
		{
			product.entity_id,
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
	],
	"crosssell_products": [
		{
			product.entity_id,
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
	],
}
```
### Configurable Product

Configurable products have variants that they can only be purchased. Please rever to variant key in below. The array of variant objects provides label and the options that are ready to be purchased. The example label from the design is `Buying Options`  in English store view. And buying options is actually an attribute of this product so variants are collected by this attribute from the catalog and listed with  two options for this product spesifically as `Once` and `with Subscription` so variant.options array should have two different products as one for `Once` and the other is `with Subscription`

Reference design [here](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A49865)

```js
{
	"entity_id": "string",
	"type": "configurable" // simple, configurable [to be added later on: virtual, gift-card, bundle, group]
	"sku": "string",
	"name": "string",
	"labels": { // conditional
		"plp": [
			{
			"type": "text",
			"text": "string",
			"position": "string"
			/**
				| ----------- | ------ | ------------ |
				| top_left    | top    | top_right    |
				| ----------- | ------ | ------------ |
				| left        | middle | right        |
				| ----------- | ------ | ------------ |
				| bottom_left | bottom | bottom_right |
				| ----------- | ------ | ------------ |
			
			**/
			}
		],
		"pdp": [
			{
			"type": "image",
			"image": "string",
			"position": "center_bottom"
			}
		]
	},
    "categories": [
		{
		  "category_id": 423,
		  "name": "string"
		}
	],
	"attributes": { // here, remaining product attributes comes dynamically
		"attribute_code": { // unique identifier of the attribute
				"label": "string", // attribute label
				"is_visible": true,
				"value": "string",
				"filterable": false,
			},
	},
	"related_products": [
	    {
		    product.entity_id,
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
	],
	"upsell_products": [
	    {
		    product.entity_id,
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
	],
	"crosssell_products": [
	    {
		    product.entity_id,
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
	],
	"variant": [
		{
			product
		}
	]
}
```

