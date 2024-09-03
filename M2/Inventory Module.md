---
type: feature
project: hmg
area: magento
module: inventory
owner: leanscale
reason: hmg-documentation
---

# Inventory

- Each [pharmacy](Pharmacy%20Module.md) has `SubInventoryCode`  that its represent an inventory code for each item. 
- And Each item can have stocks and safety stock for multiple pharmacies like below sku2.
- When there is a new [pharmacy](Pharmacy%20Module.md) that is created, We should have an Entry of the inventory code
- When there is a stock update from Downstream (eServices Middleware) this table will be update. 
	- When there is a new "SubInventoryCode" sent  by the Downstream Inventory update, New Pharmacy branch to be created with disabled state
- Magento calculates the item availability with closest branch (aproximity calculation with user's given location and branches location that statuses are enabled "true") [detailed workflow to be added here](#)



# Get Inventory API 

- From: Node API
- To: Magento API
- Method: `GET`
- API: `/rest/{store}/V1/alhabib/inventory`


## Parameters
```
listOfSkus i.e. sku1, sku2
```


## Expected Response
```json
{
	"sku1": {
		"safety_stock": number,
		"TKH_MP": number,
		"RYN_MP": number,
	},
	"sku2": {
		"safety_stock": number,
		"TKH_MP": number,
		"RYN_OBGYNP": number,
		"RYN_MP": number,
		"RYN_ERP": number,
		"QSM_MP": number,
		"OSSH_MP": number,
		"OLY_NP": number,
		"OLY_MP": number,
		"OLY_DMP": number,
		"SMM_MP": number,
		"SEM_ERP": number,
		"PSM_MP": number,
		"KMM_MP": number,
		"KEM_MP": number,
	},
	...pharmacyStockForOtherProducts
}
```

