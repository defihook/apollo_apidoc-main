---
type: apidoc
project: hmg
area: node
module: loyalty
owner: leanscale
reason: hmg-documentation
---


# Apply loyalty	
#cart #loyalty
- From: E Pharmarcy Frontend
- To: Node API
- Method: `PUT`
- API: `/api/V1/cart/loyalty`

## Request
```json
{
  "program": "LAKUM",
  "amount": 1
}
```
## Response data extends to [response format](response_format.md)
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
        "code": "lakum",
        "title": "Lakum",
        "value": 5
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




# Delete loyalty	
#cart #loyalty

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/cart/loyalty/delete`

 
## Response data extends to [response format](response_format.md)
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


# [Post MVLP]Get LAKUM history	
GET​/api​/V1​/customer/lakum/history
# [Post MVLP]Get LAKUM balance	
GET​/api​/V1​/customer/lakum/balance