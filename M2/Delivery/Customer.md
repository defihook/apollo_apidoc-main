---
type: feature
project: hmg
area: magento
module: customer
owner: alhabib
reason: hmg-documentation
---



# Get logged in customer details
#logistration
- From: Node API
- To: M2
- Method: `GET`
- API: `/api/V1/customers/me`

## Response data extends to [response format](response_format.md)
```json
{
    "id":19,
    "zip_code": "+966", . country code for numbers
    "phone_number": "944681907",
    "is_patient": false, 
    "verified_without_otp": false,
    "phone_verified": true,
    "id": 19,
    "group_id": 1,
    "default_billing": "0",
    "default_shipping": "0",
    "created_at": "2022-10-20 08:47:13",
    "updated_at": "2022-10-20 13:05:46",
    "created_in": "Default Store View",
    "email": "usman.muhammad@leanscale.com",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "dob": "YYYY-MM-DD", 
    "dob_hijri": "string", 
    "firstname_ar": "string", 
    "middlename_ar": "string", 
    "lastname_ar": "string", 
    "marital_status": "string", 
    "nationality": "string", 
    "nationality_iso_code": "string",  
    "occupation": "string", 
    "latitude": "string", 
    "longtitude": "string", 
    "national_id": "string", 
    "file_no": "string", 
    "id_type": 10, 
    "gender": 0, 
    "store_id": 1,
    "website_id": 1,
    "addresses": [],
    "disable_auto_group_change": 0,
    "extension_attributes": {
        "is_subscribed": false
    },
}

```


# Customer login via Phone Number
#logistration
- From: Node API
- To: M2
- Method: `POST`
- API: `/V1/alhabib/customers/login` 

## Request Body

```json
{
   "phone": {
        "zip_code": "+966",
        "number": "944681907"
    }
}
```

## Response data extends to [response format](response_format.md)
```json
{
    "otp_id": int,
}
```


# Customer Alhabib login
#logistration
- From: Node API
- To: M2
- Method: `POST`
- API: `/V1/alhabib/customers/external-login`

## Request Body with National ID

```json
{
    "phone": {
        "zip_code": "string",
        "number": "string"
    },
    "national_id": "string"
}
```
## Request Body with File No
```json
{
    "phone": {
        "zip_code": "string",
        "number": "string"
    },
    "file_no": "string" 
}
```

## Response data extends to [response format](response_format.md)
```json
{
    "otp_id": int,
}
```

# Verify given OTP code
#logistration #otp-verification
- From: Node API
- To: M2
- Method: `POST`
- API: `/V1/alhabib/customer/otp/check`

## Request Body

```json
{
    "otp_id": int,
    "otp_code": "string"
}
```


## Response Body for Verified Token 

```json
{
    "customer": {
        "zip_code": "+966", . country code for numbers
        "phone_number": "944681907",
        "is_patient": false, 
        "verified_without_otp": false,
        "phone_verified": true,
        "id": 19,
        "group_id": 1,
        "default_billing": "0",
        "default_shipping": "0",
        "created_at": "2022-10-20 08:47:13",
        "updated_at": "2022-10-20 13:05:46",
        "created_in": "Default Store View",
        "email": "usman.muhammad@leanscale.com",
        "firstname": "Donovan",
        "lastname": "Clements",
        "middlename": "VB",
        "dob": "YYYY-MM-DD", 
        "dob_hijri": "string", 
        "firstname_ar": "string", 
        "middlename_ar": "string", 
        "lastname_ar": "string", 
        "marital_status": "string", 
        "nationality": "string", 
        "nationality_iso_code": "string", , coming as iso not ISO, needs to change to ISO
        "occupation": "string", 
        "latitude": "string", 
        "longtitude": "string", 
        "national_id": "string", 
        "file_no": "string", 
        "id_type": 10, 
        "gender": 0, 
        "store_id": 1,
        "website_id": 1,
        "addresses": [],
        "disable_auto_group_change": 0,
        "extension_attributes": {
            "is_subscribed": false
        },
    },
    "token": "<Customer Token>"
}
```



# Customer registration
#logistration
- From: Node API
- To: M2
- Method: `POST`
- API: `/api/V1/customer/register`

## Request Body

```json
{
    "phone": {
        "zip_code": "string",
        "number": "string"
    },
    "first_name": "string",
    "last_name": "string",
    "email": "string",
    "gender": "",
    "country": "ISO Code", // only SA for now
    "city": "city_code" // share a code list with us
}
```

## [Response format](response_format.md)



# Add Customer Addresses
- From: Node API
- To: M2
- Method: `PUT`
- API: `/V1/alhabib/address/me`
-Use logged in customer token

## Request Body
```json
{
"address": { 
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "Ut error perspiciati"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97677",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "default_shipping": true,
    "default_billing": true,
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
         {
            "attribute_code": "address_label",
            "value": "ship "
        }
    ]
}
}
```
## Response data extends to [response format](response_format.md)
```json
{
    "id": 11,
    "customer_id": 24,
    "region": {
        "region_code": null,
        "region": null,
        "region_id": 0
    },
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "hello world"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97677",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
        {
            "attribute_code": "address_label",
            "value": "hello "
        }
    ]
}
```

# Update Customer Addresses
- From: Node API
- To: M2
- Method: `PUT`
- API: `/V1/alhabib/address/me`
-Use logged in customer token

## Request Body
```json
{
"address": { 
    "id": 11
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "Ut error perspiciati"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97688",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "default_shipping": true,
    "default_billing": true,
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
         {
            "attribute_code": "address_label",
            "value": "ship "
        }
    ]
}
}
```
## Response data extends to [response format](response_format.md)
```json
{
    "id": 11,
    "customer_id": 24,
    "region": {
        "region_code": null,
        "region": null,
        "region_id": 0
    },
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "hello world"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97688",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
        {
            "attribute_code": "address_label",
            "value": "hello "
        }
    ]
}
```


# Get Customer Addresses
- From: Node API
- To: M2
- Method: `GET`
- API: `/V1/customers/me/billingAddress`
-Use logged in customer token

## Response data extends to [response format](response_format.md)
```json
[
   {
    "id": 11,
    "customer_id": 24,
    "region": {
        "region_code": null,
        "region": null,
        "region_id": 0
    },
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "hello world"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97677",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "default_shipping": true,
    "default_billing": true,
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
        {
            "attribute_code": "address_label",
            "value": "hello "
        }
    ]
}
]
```

# Get Customer Addresses
- From: Node API
- To: M2
- Method: `GET`
- API: `/V1/customers/me/shippingAddress`
-Use logged in customer token

## Response data extends to [response format](response_format.md)
```json
[
   {
    "id": 11,
    "customer_id": 24,
    "region": {
        "region_code": null,
        "region": null,
        "region_id": 0
    },
    "country_id": "SA",
    "street": [
        "Ut error perspiciati",
        "hello world"
    ],
    "company": "Stuart and Houston LLC",
    "telephone": "+9955909090",
    "postcode": "97677",
    "city": "Est hic officia ulla",
    "firstname": "Donovan",
    "lastname": "Clements",
    "middlename": "VB",
    "default_shipping": true,
    "default_billing": true,
    "custom_attributes": [
        {
            "attribute_code": "latitude",
            "value": "5858"
        },
        {
            "attribute_code": "longitude",
            "value": "585"
        },
        {
            "attribute_code": "address_label",
            "value": "hello "
        }
    ]
}
]
```
# Delete Customer Addresses
- From: Node API
- To: M2
- Method: `DELETE`
- API: `/V1/alhabib/addresses/:addressId`
-Use logged in customer token

## Response data extends to [response format](response_format.md)

if address deleted.

```json
true


```



