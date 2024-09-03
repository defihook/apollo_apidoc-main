---
type: apidoc
project: hmg
area: node
module: cms
owner: leanscale
reason: hmg-documentation
---


# Get a CMS content
#cms #page #pagebuilder
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/cms​/{identifier}`

## Response data extends to [response format](response_format.md)
```js
{
  type: 'page',
  meta_title: '',
  meta_keywords: '',
  meta_description: '',
  data: [
    // Any type object that is defined under Content Types
  ]
}
```

# Get a CMS Block
#cms #page #pagebuilder
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/cms/block​/{identifier}`

## Response data extends to [response format](response_format.md)
```js
[
  ...contentTypes // Any type object that is defined under Content Types
]
```

# Content Types

1. Full banner
2. Single Banner
3. Slider
4. Product Grid and Carousel
5. Category Slider and Grid

Base response from Magento created via Blocks API to create proper structure first. We will be using same for Category Description, Product Attributes (page builder type) and Pages.

# Fullbanner
Areas that [full banner](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A50218) can be received;
- Home Page
- Category Listing Page
- Product Listing Page
- Search Result

Images are seperated for mobile and web.

## Base request & response for content

```sh
curl --location --request GET 'https://m2-alpha.alhabibpharmacydev.com/rest/default/V1/cmsBlock/full_banner_example' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <TOKEN>'
```

```json
{
  "id": 2,
  "identifier": "full_banner_example",
  "title": "Full Banner Example",
  "content": "<style>#html-body [data-pb-style=AP0G3OV]{justify-content:flex-start;display:flex;flex-direction:column;background-position:left top;background-size:cover;background-repeat:no-repeat;background-attachment:scroll}#html-body [data-pb-style=Q2DTWIW]{border-style:none}#html-body [data-pb-style=NFYA3M7],#html-body [data-pb-style=TYK5O7O]{max-width:100%;height:auto}@media only screen and (max-width: 768px) { #html-body [data-pb-style=Q2DTWIW]{border-style:none} }</style><div data-content-type=\"row\" data-appearance=\"contained\" data-element=\"main\"><div class=\"full_banner\" data-enable-parallax=\"0\" data-parallax-speed=\"0.5\" data-background-images=\"{}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"inner\" data-pb-style=\"AP0G3OV\"><figure data-content-type=\"image\" data-appearance=\"full-width\" data-element=\"main\" data-pb-style=\"Q2DTWIW\"><a href=\"https://alhabibpharmacydev.com/anyDeeplink\" target=\"\" data-link-type=\"default\" title=\"media_id_example_here\" data-element=\"link\"><img class=\"pagebuilder-mobile-hidden\" src=\"{{media url=wysiwyg/Rectangle_408.png}}\" alt=\"\" title=\"media_id_example_here\" data-element=\"desktop_image\" data-pb-style=\"NFYA3M7\"><img class=\"pagebuilder-mobile-only\" src=\"{{media url=wysiwyg/Rectangle_408_1.png}}\" alt=\"\" title=\"media_id_example_here\" data-element=\"mobile_image\" data-pb-style=\"TYK5O7O\"></a></figure></div></div>",
  "creation_time": "2022-10-25 08:23:33",
  "update_time": "2022-11-01 13:16:39",
  "active": true
}
```

## Expected JSON response

```js
{
  type: 'full_banner', //value from div.div.class as "full_banner" above as 2nd div from the top.
  id: 'media_id', //value from figure.a.title as "media_id_example_here" above
  url: 'media_url', // value from figure.a.img['mobile' or 'desktop'].url as "wysiwyg/Rectangle_408.png" above
  format: 'png, jpeg, gif, mp4',
  target: 'deepLink' // OPTIONAL: value from figure.a.href as "https://alhabibpharmacydev.com/anyDeeplink" above
}
```

# Single Banner
Areas that [single banner](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A49038) can be received;
- Home Page
- Category Listing Page
- Product Listing Page

## Base request & response for content

```sh
curl --location --request GET 'https://m2-alpha.alhabibpharmacydev.com/rest/default/V1/cmsBlock/single_banner_example' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <TOKEN>'
```

```json
{
  "id": 3,
  "identifier": "single_banner_example",
  "title": "Single Banner Example",
  "content": "<style>#html-body [data-pb-style=TMO8M4G]{justify-content:flex-start;display:flex;flex-direction:column;background-position:left top;background-size:cover;background-repeat:no-repeat;background-attachment:scroll}#html-body [data-pb-style=X0D25HQ]{border-style:none}#html-body [data-pb-style=AD2EQ4W],#html-body [data-pb-style=T6YN770]{max-width:100%;height:auto}@media only screen and (max-width: 768px) { #html-body [data-pb-style=X0D25HQ]{border-style:none} }</style><div data-content-type=\"row\" data-appearance=\"contained\" data-element=\"main\"><div class=\"single_banner\" data-enable-parallax=\"0\" data-parallax-speed=\"0.5\" data-background-images=\"{}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"inner\" data-pb-style=\"TMO8M4G\"><figure data-content-type=\"image\" data-appearance=\"full-width\" data-element=\"main\" data-pb-style=\"X0D25HQ\"><a href=\"https://alhabibpharmacydev.com/anyDeeplink\" target=\"\" data-link-type=\"default\" title=\"media_id_example_here\" data-element=\"link\"><img class=\"pagebuilder-mobile-hidden\" src=\"{{media url=wysiwyg/Rectangle_408.png}}\" alt=\"\" title=\"media_id_example_here\" data-element=\"desktop_image\" data-pb-style=\"AD2EQ4W\"><img class=\"pagebuilder-mobile-only\" src=\"{{media url=wysiwyg/Rectangle_408_1.png}}\" alt=\"\" title=\"media_id_example_here\" data-element=\"mobile_image\" data-pb-style=\"T6YN770\"></a></figure></div></div>",
  "creation_time": "2022-10-25 08:53:17",
  "update_time": "2022-11-01 13:30:43",
  "active": true
}
```

## Expected JSON response

```js
{
  type: 'single_banner', // value from div.div.class as "single_banner" above from the top
  id: 'media_id', //value from figure.a.title as "media_id_example_here" above
  url: 'media_url', // value from figure.a.img['mobile' or 'desktop'].url as "wysiwyg/Rectangle_408.png" above
  format: 'png, jpeg, gif, mp4',
  target: 'deepLink' // OPTIONAL: value from figure.a.href as "https://alhabibpharmacydev.com/anyDeeplink" above
}
```


# Slider

Areas that [slider](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A50206) can be received;
- Home Page
- Category Listing Page
- Product Listing Page

## Base request & response for content
```sh
curl --location --request GET 'https://m2-alpha.alhabibpharmacydev.com/rest/default/V1/cmsBlock/slider_example' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <TOKEN>'
```


```json
{
  "id": 4,
  "identifier": "slider_example",
  "title": "Slider Example",
  "content": "<style>#html-body [data-pb-style=XKP58UE]{justify-content:flex-start;display:flex;flex-direction:column;background-position:left top;background-size:cover;background-repeat:no-repeat;background-attachment:scroll}#html-body [data-pb-style=HRODPY1]{min-height:300px}#html-body [data-pb-style=OQ5F99G]{background-position:left top;background-size:cover;background-repeat:no-repeat}#html-body [data-pb-style=BWIPIV2]{background-color:transparent}#html-body [data-pb-style=IXO0JE4]{background-position:left top;background-size:cover;background-repeat:no-repeat}#html-body [data-pb-style=PEG5H6X]{background-color:transparent}</style><div data-content-type=\"row\" data-appearance=\"contained\" data-element=\"main\"><div class=\"slider\" data-enable-parallax=\"0\" data-parallax-speed=\"0.5\" data-background-images=\"{}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"inner\" data-pb-style=\"XKP58UE\"><div class=\"pagebuilder-slider\" data-content-type=\"slider\" data-appearance=\"default\" data-autoplay=\"false\" data-autoplay-speed=\"4000\" data-fade=\"false\" data-infinite-loop=\"false\" data-show-arrows=\"false\" data-show-dots=\"true\" data-element=\"main\" data-pb-style=\"HRODPY1\"><div data-content-type=\"slide\" data-slide-name=\"\" data-appearance=\"poster\" data-show-button=\"never\" data-show-overlay=\"never\" data-element=\"main\"><a href=\"https://alhabibpharmacydev.com/anyDeeplink\" target=\"\" data-link-type=\"default\" title=\"media_id_example_here\" data-element=\"link\"><div class=\"pagebuilder-slide-wrapper\" data-background-images=\"{\\&quot;desktop_image\\&quot;:\\&quot;{{media url=wysiwyg/desktop.png}}\\&quot;,\\&quot;mobile_image\\&quot;:\\&quot;{{media url=wysiwyg/mobile.png}}\\&quot;}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"wrapper\" data-pb-style=\"OQ5F99G\"><div class=\"pagebuilder-overlay pagebuilder-poster-overlay\" data-overlay-color=\"\" aria-label=\"\" title=\"media_id_example_here\" data-element=\"overlay\" data-pb-style=\"BWIPIV2\"><div class=\"pagebuilder-poster-content\"><div data-element=\"content\"></div></div></div></div></a></div><div data-content-type=\"slide\" data-slide-name=\"\" data-appearance=\"poster\" data-show-button=\"never\" data-show-overlay=\"never\" data-element=\"main\"><div data-element=\"empty_link\"><div class=\"pagebuilder-slide-wrapper\" data-background-images=\"{\\&quot;desktop_image\\&quot;:\\&quot;{{media url=wysiwyg/desktop.png}}\\&quot;,\\&quot;mobile_image\\&quot;:\\&quot;{{media url=wysiwyg/mobile.png}}\\&quot;}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"wrapper\" data-pb-style=\"IXO0JE4\"><div class=\"pagebuilder-overlay pagebuilder-poster-overlay\" data-overlay-color=\"\" aria-label=\"\" title=\"media_id_example_here\" data-element=\"overlay\" data-pb-style=\"PEG5H6X\"><div class=\"pagebuilder-poster-content\"><div data-element=\"content\"></div></div></div></div></div></div></div></div></div>",
  "creation_time": "2022-10-25 09:02:27",
  "update_time": "2022-11-01 13:35:56",
  "active": true
}
```

## Expected JSON response

```js
{
  type: 'slider', // value from div.div.class as "slider" above from the top
  data: [
    {
      id: 'media_id', // value from "pagebuilder-overlay" class as title "media_id_example_here" 
      url: 'media_url', // value from "pagebuilder-slide-wrapper" as url "wysiwyg/mobile.png" or ""wysiwyg/desktop.png" above
      format: 'png, jpeg, gif, mp4',
      target: 'deepLink' // OPTIONAL: value from figure.a.href as "https://alhabibpharmacydev.com/anyDeeplink" above
    }
  ]
}
```

# Product Grid and Carousel

Areas that [product grid](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A50221) can be received;
- Home Page
- Category Listing Page
- Product Listing Page
- Search Result Page
- Product Detail Page

## Base request & response for content
```sh
curl --location --request GET 'https://m2-alpha.alhabibpharmacydev.com/rest/default/V1/cmsBlock/product_grid_example' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <TOKEN>'
```

```json
{
  "id": 5,
  "identifier": "product_grid_example",
  "title": "Product Grid Example",
  "content": "<style>#html-body [data-pb-style=D77E76G]{justify-content:flex-start;display:flex;flex-direction:column;background-position:left top;background-size:cover;background-repeat:no-repeat;background-attachment:scroll}#html-body [data-pb-style=AMQWA6J]{display:inline-block}#html-body [data-pb-style=PVBQS5M]{text-align:center}</style><div data-content-type=\"row\" data-appearance=\"contained\" data-element=\"main\"><div class=\"product_grid\" data-enable-parallax=\"0\" data-parallax-speed=\"0.5\" data-background-images=\"{}\" data-background-type=\"image\" data-video-loop=\"true\" data-video-play-only-visible=\"true\" data-video-lazy-load=\"true\" data-video-fallback-src=\"\" data-element=\"inner\" data-pb-style=\"D77E76G\"><div data-content-type=\"buttons\" data-appearance=\"inline\" data-same-width=\"false\" data-element=\"main\" class=\"product_title\"><div data-content-type=\"button-item\" data-appearance=\"default\" data-element=\"main\" data-pb-style=\"AMQWA6J\"><a class=\"pagebuilder-button-primary\" href=\"https://alhabibpharmacydev.com\" target=\"\" data-link-type=\"default\" data-element=\"link\" data-pb-style=\"PVBQS5M\"><span data-element=\"link_text\">MY EXAMPLE TITLE</span></a></div></div><div data-content-type=\"products\" data-appearance=\"grid\" data-element=\"main\">{{widget type=\"Magento\\CatalogWidget\\Block\\Product\\ProductsList\" template=\"Magento_CatalogWidget::product/widget/content/grid.phtml\" anchor_text=\"\" id_path=\"\" show_pager=\"0\" products_count=\"5\" condition_option=\"category_ids\" condition_option_value=\"8\" type_name=\"Catalog Products List\" conditions_encoded=\"^[`1`:^[`aggregator`:`all`,`new_child`:``,`type`:`Magento||CatalogWidget||Model||Rule||Condition||Combine`,`value`:`1`^],`1--1`:^[`operator`:`==`,`type`:`Magento||CatalogWidget||Model||Rule||Condition||Product`,`attribute`:`category_ids`,`value`:`8`^]^]\" sort_order=\"position\"}}</div></div></div>",
  "creation_time": "2022-10-25 09:22:05",
  "update_time": "2022-11-01 13:40:43",
  "active": true
}
```

## Expected JSON response

```js
{
  type: 'product_grid', // value from div.div.class as "product_grid" or "product_carousel" above from the top
  title: 'string', // optional: find Class - product grid and one above, you will find class as "product_title" and find child span.data-element.value as "MY Example Title"
  target: 'anyDeepLink',// optional: find Class - product grid and one above, you will find class as "product_title" and find child a.href as "https://alhabibpharmacydev.com/anyDeeplink"
  product_count: 34, //find from catalog widget above
  data: [ //products fetched from catalog widget as can be category, sku, or condition result with the sortBy selection.
    {
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
  ]
}
```



# Category Slider

Areas that [category slider](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A50210) can be received;
- Home Page
- Category Listing Page

## Base request & response for content
```html
<div>

</div>
```

## Expected JSON response

```js
{
  type: 'category_slider',
  title: 'string', // optional
  target: 'anyDeepLink' // optional
  data: [
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
}
```


# Category Grid

Areas that [category grid](https://www.figma.com/file/VNkGqPWSd7ybkuvzycGvMk/Apollo-Project-(Public)?node-id=1417%3A49022) can be received;
- Home Page
- Category Listing Page

## Base request & response for content
```html
<div>

</div>
```

## Expected JSON response

```js
{
  type: 'category_grid',
  title: 'string', // optional
  target: 'anyDeepLink' // optional
  data: [
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
}
```




# Reference Page Response with Blocks

Following is the response of how Page returns for blocks that we created to make the content dynamic. We can either send Widget as block or types above like Slider or Product Grid

every block has their own content so we need to pull each cms block and draw the content with same sorting that page returns like below block id sorted as 4, 5, 2, 5

```sh
curl --location --request GET 'https://m2-alpha.alhabibpharmacydev.com/rest/default/V1/cmsPage/test-home' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <TOKEN>'
```

```json
{
    "id": 8,
    "identifier": "test-home",
    "title": "Test-home",
    "page_layout": "cms-full-width",
    "meta_title": "",
    "meta_keywords": "",
    "meta_description": "",
    "content_heading": "",
    "content": "<div data-content-type=\"block\" data-appearance=\"default\" data-element=\"main\">{{widget type=\"Magento\\Cms\\Block\\Widget\\Block\" template=\"widget/static_block/default.phtml\" block_id=\"4\" type_name=\"CMS Static Block\"}}</div><div data-content-type=\"block\" data-appearance=\"default\" data-element=\"main\">{{widget type=\"Magento\\Cms\\Block\\Widget\\Block\" template=\"widget/static_block/default.phtml\" block_id=\"5\" type_name=\"CMS Static Block\"}}</div><div data-content-type=\"block\" data-appearance=\"default\" data-element=\"main\">{{widget type=\"Magento\\Cms\\Block\\Widget\\Block\" template=\"widget/static_block/default.phtml\" block_id=\"2\" type_name=\"CMS Static Block\"}}</div><div data-content-type=\"block\" data-appearance=\"default\" data-element=\"main\">{{widget type=\"Magento\\Cms\\Block\\Widget\\Block\" template=\"widget/static_block/default.phtml\" block_id=\"5\" type_name=\"CMS Static Block\"}}</div>",
    "creation_time": "2022-10-25 10:09:47",
    "update_time": "2022-10-25 10:09:47",
    "sort_order": "0",
    "custom_theme": "",
    "active": true
}
```

## Expected JSON response from HTMLtoJSON service

```js
{
  type: 'page',
  meta_title: '',
  meta_keywords: '',
  meta_description: '',
  data: [
    { //because block_id:4 is a block that has slider type
      type: 'slider', 
      data: [
        {
          id: 'media_id', 
          url: 'media_url', 
          format: 'png, jpeg, gif, mp4',
          target: 'deepLink'
        }
      ]
    },
    { // block_id:5
      type: 'product_grid',
      title: 'string',
      target: 'anyDeepLink',
      product_count: 34,
      data: [ 
        {
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
      ]
    },
    { //block_id: 2
      type: 'full_banner', 
      id: 'media_id', 
      url: 'media_url', 
      format: 'png, jpeg, gif, mp4',
      target: 'deepLink' 
    },
    { // block_id:5
      type: 'product_grid',
      title: 'string',
      target: 'anyDeepLink',
      product_count: 34,
      data: [ 
        {
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
      ]
    },
  ]
}
```