---
type: feature
project: hmg
area: magento
module: inventory
owner: leanscale
reason: hmg-documentation
---


# Pharmacy 
We have Pharmacies that we need to have a screen at magento under Al Habib Module that allows magento users to see list of pharmacies, Edit pharmacies and add new pharmacy "who has access if the certain user role is met" 

There should be a Save after event to trigger "Elastic Indexing for updated Pharmacy" action
There should be a New record event to trigger "Create an inventory if there is no record already" action

### Expected Data that should be available in Elastic / Pharmacy

```json
[
	{
		"status": bool,
		"isFulfilment": bool,
		"organizationCode": "string",
		"SubInventoryCode": "string",
		"organizationName": "string",
		"address": "string",
		"lat": "string",
		"long": "string",
		"location": "string",
		"city": "string",
		"phone": "string",
		"workingHrs": {
			"sunday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"monday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"tuesday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"wednesday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"thursday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"friday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
			"saturday": {
				"from": "HH:MM",
				"to": "HH:MM"
			},
		}
	},
	...pharmacies
]
```



