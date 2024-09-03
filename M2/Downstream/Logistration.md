---
type: apidoc
project: hmg
area: downstream
owner: leanscale
module: customer
reason: hmg-documentation
---

# Logistration

Logistration module that communicate with HMG E Services Middleware to let patients/old users to login to the new application.

## Is Patient Exist
#login #exist-user

- From: M2
- To: EServices Middleware
- Method: `POST`
- API: `/api/customer/is_patient_exists`

### Request

Phone number that is pure and excluded from followings
- country code or ZipCode "+966"
- country code replacement as "0"

```json
{
  "phoneNo": "5368798202"
}
```

### Response

```
{ true | false }
```


## Login
#login 

- From: M2
- To: EServices Middleware
- Method: `POST`
- API: `api/customer/login`

### Request

- Type: Required to identify customer login selection whether as with National ID or with Patient ID as flag. 
- Value: According to the type, it can be National ID or PAtient ID
- Phone: Phone number that is pure and excluded from followings
  - country code or ZipCode "+966"
  - country code replacement as "0"


```json
{
  "type": "nationalId",
  "value": "16898166021",
  "phone": "5368798202",
}
```

### Response

```json
{
  "fileNo": "string",
  "zipCode": "string",
  "phoneNo": "string",
  "nationalID": "string",
  "email": "string",
  "dateOfBirth": "2022-09-07T11:42:51.887Z",
  "dateOfBirthHijri": "string",
  "name": {
    "firstName": "string",
    "middleName": "string",
    "lastName": "string",
    "firstNameAr": "string",
    "middleNameAr": "string",
    "lastNameAr": "string"
  },
  "maritalStatus": 0,
  "maritalStatusCode": "string",
  "nationality": "string",
  "nationalityISOCode": "string",
  "occupation": "string",
  "idType": 10,
  "gender": 0,
  "billingAddress": {
    "firstName": "string",
    "lastName": "string",
    "email": "string",
    "phoneNumber": "string",
    "faxNumber": "string",
    "company": "string",
    "city": "string",
    "country": "string",
    "stateProvince": "string",
    "address1": "string",
    "address2": "string",
    "zipPostalCode": "string",
    "latLong": "string"
  },
  "shippingAddress": {
    "firstName": "string",
    "lastName": "string",
    "email": "string",
    "phoneNumber": "string",
    "faxNumber": "string",
    "company": "string",
    "city": "string",
    "country": "string",
    "stateProvince": "string",
    "address1": "string",
    "address2": "string",
    "zipPostalCode": "string",
    "latLong": "string"
  }
}
```
