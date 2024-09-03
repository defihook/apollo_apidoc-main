---
type: apidoc
project: hmg
area: node
module: customer
owner: leanscale
reason: hmg-documentation
---

# Get logged in customer details
#logistration
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/customer`

## Response data extends to [response format](response_format.md)
```json
{
  "id": number,
  "group_name": "string",
  "is_patient": bool,
  "created_at": "YYYY-MM-DDTHH:MM:SS",
  "updated_at": "YYYY-MM-DDTHH:MM:SS",
  "created_in": "string",
  "dob": "YYYY-MM-DD",
  "dob_hijri": "string",
  "email": "string",
  "firstname": "string",
  "middlename": "string",
  "lastname": "string",
  "country": "SA",
  "city": "abha",
  "firstname_ar": "string",
  "middlename_ar": "string",
  "lastname_ar": "string",
  "marital_status": "string",
  "nationality": "string",
  "nationality_iso_code": "string",
  "occupation": "string",
  "gender": "string", // MALE, FEMALE
  "store_id": "string",
  "latitude": "string",
  "longtitude": "string",
  "profile_picture": "string",
  "zip_code": "string",
  "phone_number": "string",
  "national_id": "string",
  "file_no": "string",
  "id_type": 10,
}
```




# Customer registration
#logistration
- From: E Pharmarcy Frontend
- To: Node API
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
    "city": "city_code" // https://docs.google.com/spreadsheets/d/1yItliSCSXRjGdJU_d4I5M7GsmFZc30lS7mj-VysJidk/edit#gid=1963070103
}
```

##  [Response format](response_format.md)
```json
{
    "otp_id": 11,
    "otp_code": "string" // if (env.mode !== 'Production')
}
```

# Customer HMG login
#logistration
- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/hmg_login`

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

##  [Response format](response_format.md)
```json
{
    "otp_id": 11,
    "otp_code": "string" // if env.mode !== 'Production'
}
```

# Customer login
#logistration
- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/login`

## Request Body

```json
{
    "phone": {
        "zip_code": "string",
        "number": "string"
    }
}
```

##  [Response format](response_format.md)
```json
{
    "otp_id": 11,
    "otp_code": "string" // if env.mode !== 'Production'
}
```

# Verify given OTP code
#logistration #otp-verification
- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/verify_otp`

## Request Body

```json
{
    "otp_id": 11,
    "otp_code": "string"
}
```

## [Response format](response_format.md)
```json
{
    `"zip_code": "+966", . country code for numbers
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
}`
```
# Customer logout
- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/logout`

## Request Body
```
{}
```

## [Response format](response_format.md)

# Get customer address

- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/customer/address`

## Response data extends to [response format](response_format.md)

```js
[
	{
        id,
        country_id: 'SA' // default SA
        street: ["street 1", "street 2"],
        telephone: "string",
        postcode: "string"
        city,
        firstname,
        lastname,
        email,
        address_label,
        latitude,
        longitude
    }
]
```


# Add an address
- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/address`

## Request Body

```js
{
    country_id: 'SA' // default SA
    street: ["street 1", "street 2"],
    telephone: "string",
    postcode: "string"
    city,
    firstname,
    lastname,
    email,
    address_label,
    latitude,
    longitude
}
```

## Response data extends to [response format](response_format.md)

# Update addresses 
- From: E Pharmarcy Frontend
- To: Node API
- Method: `PUT`
- API: `/api/V1/customer/address/{id}`

## Request Body

```js
{
    country_id: 'SA' // default SA
    street: ["street 1", "street 2"],
    telephone: "string",
    postcode: "string"
    city,
    firstname,
    lastname,
    email,
    address_label,
    latitude,
    longitude
}
```

## Response data extends to [response format](response_format.md)

# Delete address

- From: E Pharmarcy Frontend
- To: Node API
- Method: `DELETE`
- API: `/api/V1/customer/address/{id}`

## Request Body

```json
{}
```


## Response data extends to [response format](response_format.md)





# Sends a password reset link

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/request_password_reset`

## Request Body

```json
{
    "user_identifier": "string" // email, phone, national ID, or HMG file number
}
```

## Response data extends to [response format](response_format.md)

# Verify the token for reset password

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/customer/reset_password`

## Request Body

```json
{
    "reset_password_token": "string"
}
```


## Response data extends to [response format](response_format.md)

# Update the current user’s password

- From: E Pharmarcy Frontend
- To: Node API
- Method: `PUT`
- API: `/api/V1/customer/update_password`

## Request Body

```json
{
      "current_password": "string",
      "new_password": "string"
}
```


## Response data extends to [response format](response_format.md)



# Register to Lakum loyalty program
## Response data extends to [response format](response_format.md)

# Loyalty otp
## Response data extends to [response format](response_format.md)


# List customer saved cards

- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/customer/cards`

## Response data extends to [response format](response_format.md)

```json
{
  "cards": [
    {
      "id": "string",
      "last_4_digits": "string",
      "expiration_date": "MM/YYYY",
      "requires_cvv": false,
      "payment_method": "string",
      "type": "VISA"
    },
    {
      "id": "string",
      "last_4_digits": "string",
      "expiration_date": "MM/YYYY",
      "requires_cvv": false,
      "payment_method": "string",
      "type": "MADA"
    },
  ]
}
```

## Response data extends to [response format](response_format.md)

# Delete saved credit card

- From: E Pharmarcy Frontend
- To: Node API
- Method: `DELETE`
- API: `/api/V1/customer/cards/{id}`

## Response data extends to [response format](response_format.md)



