---
type: apidoc
project: hmg
area: magento
module: loyalty
owner: leanscale
reason: hmg-documentation
---

# Add Loyalty Points
#cart #loyalty

Loyalty points has their own calculation to the actual money. i.e. 100 points equals to 5 SAR because of this formula => `actualPrice = loyaltyPoints * 0.05` this calculation has to be done on 3rd party who is the source of truth.


- From: Node
- To: M2
- Method: `POST`
- API: `/V1/alhabib/carts/mine/loyalty/`

## Request 
```json
{
  "amount": 100,
}
```



## Response data extends to [response format](./response_format.md)
#same response like get cart
```js
{
    "grand_total": 5,
    "base_grand_total": 5,
    "subtotal": 10,
    "base_subtotal": 10,
    "discount_amount": 0,
    "base_discount_amount": 0,
    "subtotal_with_discount": 10,
    "base_subtotal_with_discount": 10,
    "shipping_amount": 0,
    "base_shipping_amount": 0,
    "shipping_discount_amount": 0,
    "base_shipping_discount_amount": 0,
    "tax_amount": 0,
    "base_tax_amount": 0,
    "weee_tax_applied_amount": null,
    "shipping_tax_amount": 0,
    "base_shipping_tax_amount": 0,
    "subtotal_incl_tax": 10,
    "shipping_incl_tax": 0,
    "base_shipping_incl_tax": 0,
    "base_currency_code": "SAR",
    "quote_currency_code": "SAR",
    "items_qty": 2,
    "items": [
        {
            "item_id": 57,
            "price": 5,
            "base_price": 5,
            "qty": 2,
            "row_total": 10,
            "base_row_total": 10,
            "row_total_with_discount": 0,
            "tax_amount": 0,
            "base_tax_amount": 0,
            "tax_percent": 0,
            "discount_amount": 0,
            "base_discount_amount": 0,
            "discount_percent": 0,
            "price_incl_tax": 5,
            "base_price_incl_tax": 5,
            "row_total_incl_tax": 10,
            "base_row_total_incl_tax": 10,
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
            "value": 10
        },
        {
            "code": "giftwrapping",
            "title": "Gift Wrapping",
            "value": null,
            "extension_attributes": {
                "gw_item_ids": [],
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
                "tax_grandtotal_details": []
            }
        },
        {
            "code": "grand_total",
            "title": "Grand Total",
            "value": 5,
            "area": "footer"
        },
        {
            "code": "lakum_loyalty_discount",
            "title": "Lakum Discount",
            "value": 5
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
```


# DELETE Loyalty Points

#cart

- From: Node
- To: M2
- Method: `POST`
- API: `/V1/alhabib/carts/mine/loyalty/delete`


## Response data extends to [response format](./response_format.md)
#same response like get cart
```js
{
  "id": 1,
  "created_at": "dateTimeString",
  "updated_at": "dateTimeString",
  "is_active": 1,
  "is_virtual": 0,
  "items": [], // products in cart
  "items_count": 34,
  "items_qty": 1234,
  "customer": {
    "email": "string",
    "firstname": "string",
    "lastname": "string"
  },
  "billing_address": {
    "id": 123,
    "address_label": "string",
    "firstname": "string",
    "middlename": "string",
    "lastname": "string",
    "email": "string",
    "phone_number": "string",
    "company": "string",
    "city": "string",
    "country": "string",
    "state_province": "string",
    "address1": "string",
    "address2": "string",
    "zip_code": "string",
    "latitude": double,
    "longtitude": double,
    "same_as_billing": 0
  },
  "shipping_address": {
    "id": 234,
    "address_label": "string",
    "firstname": "string",
    "middlename": "string",
    "lastname": "string",
    "email": "string",
    "phone_number": "string",
    "company": "string",
    "city": "string",
    "country": "string",
    "state_province": "string",
    "address1": "string",
    "address2": "string",
    "zip_code": "string",
    "latitude": double,
    "longtitude": double,
    "same_as_billing": 0
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
  "store_id": 27,
  "extension_attributes": {
    "shipping_assignments": [],
    "lakum": {
      "points": 100,
      "money_equivalent": 3
    }
  },
  "totals": {
    "grand_total": 0,
    "base_grand_total": 0,
    "subtotal": 0,
    "base_subtotal": 0,
    "discount_amount": 0,
    "base_discount_amount": 0,
    "subtotal_with_discount": 0,
    "base_subtotal_with_discount": 0,
    "shipping_amount": 0,
    "base_shipping_amount": 0,
    "tax_amount": 0,
    "base_tax_amount": 0,
    "weee_tax_applied_amount": null,
    "shipping_tax_amount": 0,
    "base_shipping_tax_amount": 0,
    "subtotal_incl_tax": 0,
    "shipping_incl_tax": 0,
    "base_shipping_incl_tax": 0,
    "base_currency_code": "SAR",
    "quote_currency_code": "SAR",
    "items_qty": 0,
    "items": [],
    "total_segments": [
      {
        "code": "cash_on_delivery_fee",
        "title": "",
        "value": null
      },
      {
        "code": "subtotal",
        "title": "Subtotal",
        "value": 0
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
        "area": "taxes",
        "extension_attributes": {
          "tax_grandtotal_details": []
        }
      },
      {
        "code": "grand_total",
        "title": "Grand Total",
        "value": 0,
        "area": "footer"
      }
    ]
  }
}
```