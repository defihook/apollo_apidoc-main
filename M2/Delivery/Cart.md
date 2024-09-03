---
type: apidoc
project: hmg
area: magento
owner: leanscale
module: cart
reason: hmg-documentation
---

# Create a Cart
#cart

- From: Node API
- To: M2
- Method: `POST`
- API:
  - GUEST: `/rest/V1/guest-carts`
  - CUSTOMER: `/rest/V1/carts/mine`


## Response data extends to [response format](./response_format.md)

```raw
{quoteId}
```

# Get Cart Details
#cart

- From: Node API
- To: M2
- Method: `GET`
- API:
  - GUEST: `/rest/V1/guest-carts/{qoute_id}`
  - CUSTOMER: `/rest/V1/carts/mine`

## Response data extends to [response format](./response_format.md)
```json
{
  "id": 105,
  "store_id": 2,
  "created_at": "2022-11-02 07:42:54",
  "updated_at": "2022-11-02 07:42:57",
  "is_active": true,
  "is_virtual": false,
  "items": [
    {
      "item_id": 43,
      "sku": "Romans",
      "qty": 1,
      "name": "Romans",
      "price": 99,
      "product_type": "simple",
      "quote_id": "u0pywIOxdYp5L57tYAHotJTVarCiZsLX"
    }
  ],
  "items_count": 1,
  "items_qty": 1,
  "customer": {
    "phone_number": null,
    "file_no": null,
    "national_id": null,
    "date_of_birth_hijri": null,
    "marital_status": null,
    "marital_status_code": null,
    "nationality_iso_code": null,
    "occupation": null,
    "id_type": null,
    "zip_code": null,
    "is_patient": null,
    "first_name_ar": null,
    "last_name_ar": null,
    "middle_name_ar": null,
    "nationality": null,
    "email": null,
    "firstname": null,
    "lastname": null
  },
  "billing_address": {
	"country_id": "SA",
	"street": ["stree1", "street2"],
	"telephone": "+903450530886",
	"postcode": "4000001",
	"city": "Abha",
	"firstname": "Test", 
	"lastname": "Test",
	"email": "murat.aydin+OKV1CHE0U4@leanscale.com",
	"custom_attributes": [
	  {
		"attribute_code": "adress_label",
		"value": "string"
	  },
	  {
		"attribute_code": "latitude",
		"value": "25.35418813024048"
	  }, 
	  {
		"attribute_code": "longitude",
		"value": "55.425414383984354"
	  }
	]
  },
  "shipping_address": {
  "country_id": "SA",
	"street": ["stree1", "street2"],
	"telephone": "+903450530886",
	"postcode": "4000001",
	"city": "Abha",
	"firstname": "Test", 
	"lastname": "Test",
	"email": "murat.aydin+OKV1CHE0U4@leanscale.com",
	"same_as_billing": 0,
    "save_in_address_book": 0,
	"custom_attributes": [
	  {
		"attribute_code": "adress_label",
		"value": "string"
	  },
	  {
		"attribute_code": "latitude",
		"value": "25.35418813024048"
	  }, 
	  {
		"attribute_code": "longitude",
		"value": "55.425414383984354"
	  }
	]
  },
  "orig_order_id": 0,
  "currency": {
    "global_currency_code": "SAR",
    "base_currency_code": "SAR",
    "store_currency_code": "SAR",
    "quote_currency_code": "SAR",
    "store_to_base_rate": 0,
    "store_to_quote_rate": 0,
    "base_to_global_rate": 1,
    "base_to_quote_rate": 1
  },
  "customer_is_guest": true,
  "totals": {
    "grand_total": 104,
    "base_grand_total": 104,
    "subtotal": 99,
    "base_subtotal": 99,
    "discount_amount": 0,
    "base_discount_amount": 0,
    "subtotal_with_discount": 99,
    "base_subtotal_with_discount": 99,
    "shipping_amount": 5,
    "base_shipping_amount": 5,
    "shipping_discount_amount": 0,
    "base_shipping_discount_amount": 0,
    "tax_amount": 0,
    "base_tax_amount": 0,
    "weee_tax_applied_amount": null,
    "shipping_tax_amount": 0,
    "base_shipping_tax_amount": 0,
    "subtotal_incl_tax": 99,
    "shipping_incl_tax": 5,
    "base_shipping_incl_tax": 5,
    "base_currency_code": "SAR",
    "quote_currency_code": "SAR",
    "items_qty": 1,
    "items": [
      {
        "item_id": 43,
        "price": 99,
        "base_price": 99,
        "qty": 1,
        "row_total": 99,
        "base_row_total": 99,
        "row_total_with_discount": 0,
        "tax_amount": 0,
        "base_tax_amount": 0,
        "tax_percent": 0,
        "discount_amount": 0,
        "base_discount_amount": 0,
        "discount_percent": 0,
        "price_incl_tax": 99,
        "base_price_incl_tax": 99,
        "row_total_incl_tax": 99,
        "base_row_total_incl_tax": 99,
        "options": "[]",
        "weee_tax_applied_amount": null,
        "weee_tax_applied": null,
        "name": "Romans"
      }
    ],
    "total_segments": [
      {
        "code": "subtotal",
        "title": "Subtotal",
        "value": 99
      },
      {
        "code": "giftwrapping",
        "title": "Gift Wrapping",
        "value": null,
        "extension_attributes": {
          "gw_item_ids": [
            
          ],
          "gw_price": "0.0000",
          "gw_base_price": "0.0000",
          "gw_items_price": "0.0000",
          "gw_items_base_price": "0.0000",
          "gw_card_price": "0.0000",
          "gw_card_base_price": "0.0000"
        }
      },
      {
        "code": "shipping",
        "title": "Shipping & Handling (Flat Rate - Fixed)",
        "value": 5
      },
      {
        "code": "tax",
        "title": "Tax",
        "value": 0,
        "extension_attributes": {
          "tax_grandtotal_details": [
            
          ]
        }
      },
      {
        "code": "grand_total",
        "title": "Grand Total",
        "value": 104,
        "area": "footer"
      },
      {
        "code": "customerbalance",
        "title": "Store Credit",
        "value": -0
      },
      {
        "code": "reward",
        "title": "0 Reward points",
        "value": -0
      }
    ]
  }
}
```

# Add Items to the Cart
#cart

- From: Node API
- To: M2
- Method: `POST`
- API:
   - GUEST: `V1/guest-carts/{guest_cart_id}/items`
   - CUSTOMER: `/rest/V1/carts/mine/items`

## Request
```json
{
  "cartItem": {
    "sku": "test",
    "qty": 1,
    "quote_id": "guest_cart_id", // Optional for Customer, Required for Guest
    "extension_attributes": [] // Optional 
  }
}
```

## Response data extends to [response format](./response_format.md)
```json
{
  "id": 99,
  "store_id": 1,
  "created_at": "2022-11-02 10:49:43",
  "updated_at": "2022-11-02 10:49:43",
  "is_active": true,
  "is_virtual": false,
  "items": [
    {
      "item_id": 89,
      "sku": "test",
      "qty": 1,
      "name": "Test",
      "price": 98,
      "product_type": "simple",
      "quote_id": "CT33Tf2bIY8fVluJZIIXZfdG0BuyZQyK"
    }
  ],
  "items_count": 1,
  "items_qty": 1,
  "customer": {
    "phone_number": null,
    "file_no": null,
    "national_id": null,
    "date_of_birth_hijri": null,
    "marital_status": null,
    "marital_status_code": null,
    "nationality_iso_code": null,
    "occupation": null,
    "id_type": null,
    "zip_code": null,
    "is_patient": null,
    "first_name_ar": null,
    "last_name_ar": null,
    "middle_name_ar": null,
    "nationality": null,
    "email": null,
    "firstname": null,
    "lastname": null
  },
  "billing_address": {
    "id": 254,
    "region": null,
    "region_id": null,
    "region_code": null,
    "country_id": null,
    "street": [
      ""
    ],
    "telephone": null,
    "postcode": null,
    "city": null,
    "firstname": null,
    "lastname": null,
    "email": null,
    "same_as_billing": 0,
    "save_in_address_book": 0
  },
  "shipping_address": {
    "id": 255,
    "region": null,
    "region_id": null,
    "region_code": null,
    "country_id": null,
    "street": [
      ""
    ],
    "telephone": null,
    "postcode": null,
    "city": null,
    "firstname": null,
    "lastname": null,
    "email": null,
    "same_as_billing": 1,
    "save_in_address_book": 0
  },
  "orig_order_id": 0,
  "currency": {
    "global_currency_code": "BHD",
    "base_currency_code": "BHD",
    "store_currency_code": "BHD",
    "quote_currency_code": "BHD",
    "store_to_base_rate": 0,
    "store_to_quote_rate": 0,
    "base_to_global_rate": 1,
    "base_to_quote_rate": 1
  },
  "customer_is_guest": true,
  "totals": {
    "grand_total": 98,
    "base_grand_total": 98,
    "subtotal": 98,
    "base_subtotal": 98,
    "discount_amount": 0,
    "base_discount_amount": 0,
    "subtotal_with_discount": 98,
    "base_subtotal_with_discount": 98,
    "shipping_amount": 0,
    "base_shipping_amount": 0,
    "shipping_discount_amount": 0,
    "base_shipping_discount_amount": 0,
    "tax_amount": 0,
    "base_tax_amount": 0,
    "weee_tax_applied_amount": null,
    "shipping_tax_amount": 0,
    "base_shipping_tax_amount": 0,
    "subtotal_incl_tax": 98,
    "shipping_incl_tax": 0,
    "base_shipping_incl_tax": 0,
    "base_currency_code": "BHD",
    "quote_currency_code": "BHD",
    "items_qty": 1,
    "items": [
      {
        "item_id": 89,
        "price": 98,
        "base_price": 98,
        "qty": 1,
        "row_total": 98,
        "base_row_total": 98,
        "row_total_with_discount": 0,
        "tax_amount": 0,
        "base_tax_amount": 0,
        "tax_percent": 0,
        "discount_amount": 0,
        "base_discount_amount": 0,
        "discount_percent": 0,
        "price_incl_tax": 98,
        "base_price_incl_tax": 98,
        "row_total_incl_tax": 98,
        "base_row_total_incl_tax": 98,
        "options": "[]",
        "weee_tax_applied_amount": null,
        "weee_tax_applied": null,
        "name": "Test"
      }
    ],
    "total_segments": [
      {
        "code": "subtotal",
        "title": "Subtotal",
        "value": 98
      },
      {
        "code": "giftwrapping",
        "title": "Gift Wrapping",
        "value": null,
        "extension_attributes": {
          "gw_item_ids": [
            
          ],
          "gw_price": "0.0000",
          "gw_base_price": "0.0000",
          "gw_items_price": "0.0000",
          "gw_items_base_price": "0.0000",
          "gw_card_price": "0.0000",
          "gw_card_base_price": "0.0000"
        }
      },
      {
        "code": "shipping",
        "title": "Shipping & Handling",
        "value": 0
      },
      {
        "code": "tax",
        "title": "Tax",
        "value": 0,
        "extension_attributes": {
          "tax_grandtotal_details": [
            
          ]
        }
      },
      {
        "code": "grand_total",
        "title": "Grand Total",
        "value": 98,
        "area": "footer"
      },
      {
        "code": "customerbalance",
        "title": "Store Credit",
        "value": -0
      },
      {
        "code": "reward",
        "title": "0 Reward points",
        "value": -0
      }
    ]
  }
}
```


# Set Billing Address
#cart

- From: Node API
- To: M2
- Method: `POST`
- API:
  - GUEST: `/V1/guest-carts/{guest_cart_id}/billing-address`
  - CUSTOMER: `/V1/carts/mine/billing-address`

## Request

```json
{
  address: {
    "country_id": "SA",
    "street": ["stree1", "street2"],
    "telephone": "+903450530886",
    "postcode": "4000001",
    "city": "Abha",
    "firstname": "Test", 
    "lastname": "Test",
    "email": "murat.aydin+OKV1CHE0U4@leanscale.com",
    "custom_attributes": [
      {
      "attribute_code": "adress_label",
      "value": "string"
      },
      {
      "attribute_code": "latitude",
      "value": "25.35418813024048"
      }, 
      {
      "attribute_code": "longitude",
      "value": "55.425414383984354"
      }
    ]
  }
}
```

## Response data extends to [response format](./response_format.md)

```raw
{address_id}
```

# Get Available Shipping Methods
#cart

- From: Node
- To: M2
- Method: `GET`
- API: `/V1/alhabib/available-shipping-methods`

## Response data extends to [response format](./response_format.md)

```json
[
  {
    "title": "Flat Rate",
    "code": "flatrate",
    "price": 5
  }
]
```

# Set Shipping Address
#cart

- From: Node
- To: M2
- Method: `POST`
- API:
  - GUEST: `/V1/guest-carts/{guest_cart_id}/shipping-information`
  - CUSTOMER: `/V1/carts/mine/shipping-information`

## Request

```json
{
    "addressInformation": {
        "shipping_address": {
          "country_id": "SA",
          "street": ["stree1", "street2"],
          "telephone": "+903450530886",
          "postcode": "4000001",
          "city": "Abha",
          "firstname": "Test", 
          "lastname": "Test",
          "email": "murat.aydin+OKV1CHE0U4@leanscale.com",
          "same_as_billing": 0,
          "save_in_address_book": 0,
          "custom_attributes": [
            {
            "attribute_code": "adress_label",
            "value": "string"
            },
            {
            "attribute_code": "latitude",
            "value": "25.35418813024048"
            }, 
            {
            "attribute_code": "longitude",
            "value": "55.425414383984354"
            }
          ]
        },
        "billing_address": {
            {
              "country_id": "SA",
              "street": ["stree1", "street2"],
              "telephone": "+903450530886",
              "postcode": "4000001",
              "city": "Abha",
              "firstname": "Test", 
              "lastname": "Test",
              "email": "murat.aydin+OKV1CHE0U4@leanscale.com",
              "same_as_billing": 0,
              "save_in_address_book": 0,
              "custom_attributes": [
                {
                "attribute_code": "adress_label",
                "value": "string"
                },
                {
                "attribute_code": "latitude",
                "value": "25.35418813024048"
                }, 
                {
                "attribute_code": "longitude",
                "value": "55.425414383984354"
                }
              ]
            }
        },
        "shipping_method_code": "flatrate",
        "shipping_carrier_code": "flatrate"
    }
},
```

## Response data extends to [response format](./response_format.md)

```json
{
  "payment_methods": [
    {
      "code": "checkmo",
      "title": "Check \/ Money order"
    }
  ],
  "totals": {
    "grand_total": 94.1,
    "base_grand_total": 94.1,
    "subtotal": 99,
    "base_subtotal": 99,
    "discount_amount": -9.9,
    "base_discount_amount": -9.9,
    "subtotal_with_discount": 89.1,
    "base_subtotal_with_discount": 89.1,
    "shipping_amount": 5,
    "base_shipping_amount": 5,
    "shipping_discount_amount": 0,
    "base_shipping_discount_amount": 0,
    "tax_amount": 0,
    "base_tax_amount": 0,
    "weee_tax_applied_amount": null,
    "shipping_tax_amount": 0,
    "base_shipping_tax_amount": 0,
    "subtotal_incl_tax": 99,
    "shipping_incl_tax": 5,
    "base_shipping_incl_tax": 5,
    "base_currency_code": "BHD",
    "quote_currency_code": "BHD",
    "coupon_code": "COUPON2022",
    "items_qty": 1,
    "items": [
      {
        "item_id": 34,
        "price": 99,
        "base_price": 99,
        "qty": 1,
        "row_total": 99,
        "base_row_total": 99,
        "row_total_with_discount": 0,
        "tax_amount": 0,
        "base_tax_amount": 0,
        "tax_percent": 0,
        "discount_amount": 9.9,
        "base_discount_amount": 9.9,
        "discount_percent": 10,
        "price_incl_tax": 99,
        "base_price_incl_tax": 99,
        "row_total_incl_tax": 99,
        "base_row_total_incl_tax": 99,
        "options": "[]",
        "weee_tax_applied_amount": null,
        "weee_tax_applied": null,
        "name": "Romans"
      }
    ],
    "total_segments": [
      {
        "code": "subtotal",
        "title": "Subtotal",
        "value": 99
      },
      {
        "code": "giftwrapping",
        "title": "Gift Wrapping",
        "value": null,
        "extension_attributes": {
          "gw_item_ids": [
            
          ],
          "gw_price": "0.0000",
          "gw_base_price": "0.0000",
          "gw_items_price": "0.0000",
          "gw_items_base_price": "0.0000",
          "gw_card_price": "0.0000",
          "gw_card_base_price": "0.0000"
        }
      },
      {
        "code": "discount",
        "title": "Discount (COUPON2022)",
        "value": -9.9
      },
      {
        "code": "shipping",
        "title": "Shipping & Handling (Flat Rate - Fixed)",
        "value": 5
      },
      {
        "code": "tax",
        "title": "Tax",
        "value": 0,
        "extension_attributes": {
          "tax_grandtotal_details": [
            
          ]
        }
      },
      {
        "code": "grand_total",
        "title": "Grand Total",
        "value": 94.1,
        "area": "footer"
      },
      {
        "code": "customerbalance",
        "title": "Store Credit",
        "value": -0
      },
      {
        "code": "reward",
        "title": "0 Reward points",
        "value": -0
      }
    ],
    "extension_attributes": {
      "reward_points_balance": 0,
      "reward_currency_amount": 0,
      "base_reward_currency_amount": 0
    }
  }
}
```

# Place Order
#cart

- From: Node
- To: M2
- Method: `PUT`
- API:
  - GUEST: `/V1/guest-carts/{guest_cart_id}/order`
  - CUSTOMER: `/V1/carts/mine/order`

## Request
### Params
 - method: cashondelivery

```json
{
  "paymentMethod": {
    "method": "{payment_method_code}",
    "additional_data": {
      "key": "value"
    }
  }
}
```

### Peyfort Request
 - method: aps_fort_cc, aps_fort_vault, aps_apple
```json
{
  "paymentMethod": {
    "method": "{payment_method_code}",
    "additional_data": {
      "return_url":"https:\/\/m2-alpha.alhabibpharmacydev.com\/handlepayfort.php",
      "saved_card": true //(default false)
    }
  }
}
```

## Response data extends to [response format](./response_format.md)

```json
{
  "increment_id": "000000016",
  "order_id": 15,
  "order": {
    "applied_rule_ids": "1",
    "base_currency_code": "BHD",
    "base_discount_amount": -9.8,
    "base_grand_total": 93.2,
    "base_discount_tax_compensation_amount": 0,
    "base_shipping_amount": 5,
    "base_shipping_discount_amount": 0,
    "base_shipping_discount_tax_compensation_amnt": 0,
    "base_shipping_incl_tax": 5,
    "base_shipping_tax_amount": 0,
    "base_subtotal": 98,
    "base_subtotal_incl_tax": 98,
    "base_tax_amount": 0,
    "base_total_due": 93.2,
    "base_to_global_rate": 1,
    "base_to_order_rate": 1,
    "billing_address_id": 30,
    "coupon_code": "COUPON2022",
    "created_at": "2022-10-30 14:46:16",
    "customer_email": "murat.aydin+QJ5L4CH3WI@leanscale.com",
    "customer_firstname": "Test",
    "customer_is_guest": 1,
    "customer_lastname": "Test",
    "customer_note_notify": 1,
    "discount_amount": -9.8,
    "discount_description": "COUPON2022",
    "entity_id": 15,
    "global_currency_code": "BHD",
    "grand_total": 93.2,
    "discount_tax_compensation_amount": 0,
    "increment_id": "000000016",
    "is_virtual": 0,
    "order_currency_code": "BHD",
    "protect_code": "ebd3e246ee617ef8f65abfd46b4a666f",
    "quote_id": 87,
    "remote_ip": "192.168.64.2",
    "shipping_amount": 5,
    "shipping_description": "Flat Rate - Fixed",
    "shipping_discount_amount": 0,
    "shipping_discount_tax_compensation_amount": 0,
    "shipping_incl_tax": 5,
    "shipping_tax_amount": 0,
    "state": "new",
    "status": "pending",
    "store_currency_code": "BHD",
    "store_id": 1,
    "store_name": "Main Website\nMain Website Store\nDefault Store View",
    "store_to_base_rate": 0,
    "store_to_order_rate": 0,
    "subtotal": 98,
    "subtotal_incl_tax": 98,
    "tax_amount": 0,
    "total_due": 93.2,
    "total_item_count": 1,
    "total_qty_ordered": 1,
    "updated_at": "2022-10-30 14:46:16",
    "weight": 0,
    "items": [
      {
        "applied_rule_ids": "1",
        "base_discount_amount": 9.8,
        "base_discount_tax_compensation_amount": 0,
        "base_original_price": 98,
        "base_price": 98,
        "base_price_incl_tax": 98,
        "base_row_total": 88.2,
        "base_row_total_incl_tax": 88.2,
        "base_tax_amount": 0,
        "created_at": "2022-10-30 14:46:16",
        "discount_amount": 9.8,
        "discount_percent": 10,
        "free_shipping": 0,
        "discount_tax_compensation_amount": 0,
        "is_qty_decimal": 0,
        "is_virtual": 0,
        "item_id": 15,
        "name": "Test",
        "order_id": 15,
        "original_price": 98,
        "price": 98,
        "price_incl_tax": 98,
        "product_id": 12,
        "product_type": "simple",
        "qty_ordered": 1,
        "quote_item_id": 77,
        "row_total": 88.2,
        "row_total_incl_tax": 88.2,
        "row_weight": 0,
        "sku": "Test",
        "store_id": 1,
        "tax_amount": 0,
        "tax_percent": 0,
        "updated_at": "2022-10-30 14:46:16"
      }
    ],
    "billing_address": {
      "address_type": "billing",
      "city": "Mumbai",
      "country_id": "IN",
      "email": "murat.aydin+QJ5L4CH3WI@leanscale.com",
      "entity_id": 30,
      "firstname": "Test",
      "lastname": "Test",
      "parent_id": 15,
      "postcode": "4000001",
      "region": "Maharashtra",
      "region_code": "MH",
      "region_id": 589,
      "street": [
        "221,Baker-street (e)"
      ],
      "telephone": "+908156407823"
    },
    "payment": {
      "account_status": null,
      "additional_information": [
        "Check \/ Money order"
      ],
      "amount_ordered": 93.2,
      "base_amount_ordered": 93.2,
      "base_shipping_amount": 5,
      "cc_last4": null,
      "entity_id": 15,
      "method": "checkmo",
      "parent_id": 15,
      "shipping_amount": 5
    },
    "status_histories": [
      
    ],
    "extension_attributes": {
      "item_applied_taxes": [
        
      ],
      "gift_cards": [
        
      ],
      "base_gift_cards_amount": 0,
      "gift_cards_amount": 0,
      "gw_base_price": "",
      "gw_price": "",
      "gw_items_base_price": "",
      "gw_items_price": "",
      "gw_card_base_price": "",
      "gw_card_price": ""
    }
  }
}
```

# Get payfort paramaters for order
#cart

- From: Node
- To: M2
- Method: `GET`
- API: `/V1/alhabib/aps-request-params/{orderId}`

## Response data extends to [response format](./response_format.md)
```json
{
    "increment_id": "2000000009",
    "order_id": 12,
    "payfort_param": [{
        "merchant_identifier": "ipxnRXXq",
        "access_code": "gydu4PUXsmZbAfn2lyHT",
        "merchant_reference": "2000000009",
        "language": "en",
        "currency": null,
        "amount": null,
        "customer_email": null,
        "command": null,
        "return_url": "https:\/\/m2-alpha.alhabibpharmacydev.com\/handlepayfort.php",
        "signature": "86768913ca276c37d8571f5959a2dea16e732adac6ccb5a50998f4d39e942b37",
        "service_command": "TOKENIZATION",
        "request_phrase": null,
        "sha_type": null,
        "token_name": null
    }],
    "url": "https:\/\/sbcheckout.payfort.com\/FortAPI\/paymentPage",
    "magento_response_url": "https:\/\/m2-alpha.alhabibpharmacydev.com\/amazonpaymentservicesfort\/payment\/merchantPageResponse"
}
```
