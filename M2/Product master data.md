---
type: feature
project: hmg
area: magento
owner: leanscale
module: catalog
reason: hmg-documentation
---

# Product Create
- From: E-Services Middleware
- To: E-pharmacy Backend
- Method: `POST`
- API: `/api/eservices/product`

### Expected request
```js
{
	oracleId: "**Unique ID for integration**",
	ITEM_CODE, // aka SKU
	DESCRIPTION_US, // aka product name
	DESCRIPTION_AR,
	LONG_DESCRIPTION_US,
	LONG_DESCRIPTION_AR,
	PRIMARY_UNIT_OF_MEASURE,
	ECOMMERCE_CATEGORY_ID,
	GROUP_SUBGROUP_CATEGORY_ID,
	UNIT_WEIGHT,
	WEIGHT_UOM_CODE,
	SFDA_CODE,
	SHORT_DESCRIPTION_US,
	SHORT_DESCRIPTION_AR,
	BRAND_US,
	BRAND_AR,
	STORAGE_US,
	STORAGE_AR,
	COMPOSITION,
	SPF,
	MANUFACTURER_COUNTRY_CODE,
	MANUFACTURER_COUNTRY_NAME_US,
	MANUFACTURER_COUNTRY_NAME_AR,
	SALES_PRICE,
	VAT_RATE,
}
```


### Expected Response
```JS
{
	EPHARMACY_ID: "Unique ID for integration",
	RETURN_STATUS,
	RETURN_MESSAGE,
}
```


# Product Update
- From: E-Services Middleware
- To: E-pharmacy Backend
- Method: `PUT`
- API: `/api/eservices/product`

### Expected request
```JS
{
	oracleId: "**Unique ID for integration**",
	ITEM_CODE, // aka SKU
	DESCRIPTION_US, // aka product name
	DESCRIPTION_AR,
	LONG_DESCRIPTION_US,
	LONG_DESCRIPTION_AR,
	PRIMARY_UNIT_OF_MEASURE,
	ECOMMERCE_CATEGORY_ID,
	GROUP_SUBGROUP_CATEGORY_ID,
	UNIT_WEIGHT,
	WEIGHT_UOM_CODE,
	SFDA_CODE,
	SHORT_DESCRIPTION_US,
	SHORT_DESCRIPTION_AR,
	BRAND_US,
	BRAND_AR,
	STORAGE_US,
	STORAGE_AR,
	COMPOSITION,
	SPF,
	MANUFACTURER_COUNTRY_CODE,
	MANUFACTURER_COUNTRY_NAME_US,
	MANUFACTURER_COUNTRY_NAME_AR,
	SALES_PRICE,
	VAT_RATE,
}
```


### Expected Response
```JS
{
	EPHARMACY_ID: "Unique ID for integration",
	RETURN_STATUS,
	RETURN_MESSAGE,
}
```








# Merchandising Category Create
- From: E-Services Middleware
- To: E-pharmacy Backend
- Method: `POST`
- API: `/api/eservices/category`

### Expected request
```JS
{
	oracleId: "**Unique ID for integration**",
	category_id,
	category_code,
	category_name_us,
	category_name_ar,
	enabled_flag,
	CategoryParentID,
	category_type, //(ECOMMERCE_CATEGORY or GROUP_SUBGROUP_CATEGORY)
}
```


### Expected Response
```js
{
	EPHARMACY_ID: "Unique ID for integration",
	RETURN_STATUS,
	RETURN_MESSAGE,
}
```


# Merchandising Category Update
- From: E-Services Middleware
- To: E-pharmacy Backend
- Method: `PUT`
- API: `/api/eservices/category`

### Expected request
```JS
{
	oracleId: "**Unique ID for integration**",
	category_id,
	category_code,
	category_name_us,
	category_name_ar,
	enabled_flag,
	CategoryParentID,
	category_type, //(ECOMMERCE_CATEGORY or GROUP_SUBGROUP_CATEGORY)
}
```


### Expected Response
```js
{
	EPHARMACY_ID: "Unique ID for integration",
	RETURN_STATUS,
	RETURN_MESSAGE,
}
```

# Get on-hand stock
- From: E-pharmacy Backend
- To: E-Services Middleware
- Method: `GET`
- API: `eservices/product/inventory?pharmacy=${pharmacyId1},${pharmacyId2}&sku=${sku1},${sku2}`


### Expected request
```
Params: SKU?, pharmacy? 
Desc: The E-Services middleware returns True or False if the products are available with the given pharmacies.
```


### Expected Response
```
[
	{
		SKU,
		available: Boolean
	}
]
```




# Daily Inventory [Batch]
- From: E-Services Middleware
- To: E-pharmacy Backend
- Method: `POST`
- API: `/api/eservices/batch-inventory`

### Expected request
```js
{
	oracleId: "**Unique ID for integration**",
	item_code,
	organization_code,
	subinventory_code,
	onhand_qty
}
```


### Expected Response
```js
{
	EPHARMACY_ID: "Unique ID for integration",
	RETURN_STATUS,
	RETURN_MESSAGE,
}
```



# Prescription details by Prescription ID
- From: E-Services Backend
- To: E-pharmacy Middleware
- Method: `GET`
- API: `/api/eservices/prescriptions/{prescriptionId}`

### Expected request
```
Params: prescriptionId
```


### Expected Response
```js
let res = 
{
	prescriptionId,
	appointment: {
		doctorName,
		doctorImageUrl,
		profession,
		appointmentId,
		clinic,
		hospital,
		appointment_date,
	},
	patientId,
	nationalId,
	createdAt,
	isRefillable, (bool)
	totalRefilAmount: 5,
	remainingRefilAmount: 4,
	refilHistory: [
		{
			orderId,
			orderDate,
			orderedFrom, (e-pharmacy, pharmacy-1, pharmacy-2, pharmacy-3)
		}
	]
	totalItems: 2
	items: [
		{
			sku,
			basePrice, (float)
			tax, (float)
			companyShare, (float)
			patientShare, (float)
			isClaimable, (bool)
			isInsured, (bool)
		}
	]
	totals: {
		totalPatientShare,
		totalCompanyShare,
		totalPrescription,                
	}
}
```


# Prescription list by Patient ID or National ID
- From: E-Services Backend
- To: E-pharmacy Middleware
- Method: `GET`
- API: `/api/eservices/prescriptions?{...params}`

### Expected request
```
Params: patientID? or nationalID?
```

### Expected response
```js
let res = 
[
	{
		prescriptionId,
		appointment: {
			doctorName,
			doctorImageUrl,
			profession,
			appointmentId,
			clinic,
			hospital,
			appointment_date,
		},
		patientId,
		nationalId,
		createdAt,
		isRefillable, (bool)
		totalRefilAmount: 5,
		remainingRefilAmount: 4,
		refilHistory: [
			{
				orderId,
				orderDate,
				orderedFrom, (e-pharmacy, pharmacy-1, pharmacy-2, pharmacy-3)
			}
		]
		totalItems: 2
		items: [
			{
				sku,
				basePrice, (float)
				tax, (float)
				companyShare, (float)
				patientShare, (float)
				isClaimable, (bool)
				isInsured, (bool)
			}
		]
		totals: {
			totalPatientShare,
			totalCompanyShare,
			totalPrescription,                
		}
	},
	...prescriptions
]
```







# Order creation to downstream
- From: E-pharmacy Backend
- To: E-Services Middleware
- Method: `POST`
- API: `/api/eservices/orders/create`

### Expected request
```
{
	orderId,
	orderDate,
	placedFrom: EPMAIN, (assumed e-pharmacy has a unique branch id just like pyhsical pharmacies. i.e. Saudi pharmacy is SA01, E-pharmachy's branch id is EPMAIN (E-pharmacy main))
	patientFullname,
	patientPhone
	shipmentType: string (home_delivery, store_pickup, home_delivery_express) 
	shipmentAddress: string,
	billingAddress: string
	mainDeliveryBranch: string, (branch_ids SA01, SA02, RY01, RY02)
	subDeliveryBranch: string, (branch_ids SA01, SA02, RY01, RY02)
	isPrescription: bool,
	prescriptionId?,
	discountProvider?: string, (types: internal, 3rdparty),
	items: [
		{
			SKU,
			qty,
			price,
			tax,
			discount,
			isPrescription: bool
			prescriptionId?,
			discountCode?
		}
		...skus
	],
	payment: {
		paymentType: string, (types: CC, COD, PAYPAL, APPLE_PAY)
		authId,
		totalPaid: float 
		currency: string
		totalDiscount: float
		totalTax: float
		totalStore_credit: float
		totalCompany_share: float
		totalPatient_share: float
		totalLakum: float ( converted to ),
		discountCode?: string
	},
}
```


### Expected Response
```
{
	status,
	message,
	VIDASalesOrderId
}
```

# Get invoice from downstream
- From: E-pharmacy Backend
- To: E-Services Middleware
- Method: `GET`
- API: `/api/eservices/orders/{VIDASalesOrderId}/invoice?invoiceType={invoiceTypeString}`

```js
let res = 
{
	patientId, 
	VIDAInvoiceId
	VIDASalesOrderId,
	orderDate,
	invoiceDate,
	branch?,
	items: [
		{
			SKU,
			qty,
			price,
			tax,
			discount,
			isPrescription: bool
			prescriptionId?,
			discountCode?
		}
		...skus
	],
	payment: {
		paymentType: string, (types: CC, COD, PAYPAL, APPLE_PAY)
		authId,
		totalPaid: float 
		currency: string
		totalDiscount: float
		totalTax: float
		totalStore_credit: float
		totalCompany_share: float
		totalPatient_share: float
		totalLakum: float ( converted to ),
		discountCode?: string
	},
}
```