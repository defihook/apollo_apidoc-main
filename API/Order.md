---
type: apidoc
project: hmg
area: node
module: order
owner: leanscale
reason: hmg-documentation
---

[WIP]

# Customer order list
#order  
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/customer/orders`

## Response data extends to [response format](response_format.md)
```js
[
	{
		entity_id: number,
		increment_id: number,
		created_at: "DATE",
		expected_delivery_date: "DATE", // Optional
		status: "string",
		state: "string",
		total_amount: number,
		currency: "string",
		total_qty_ordered: number,
		items: [
			{
				product_id: number
				sku: number,
				media: "string",
			},
		],
		shipping_adress: {
			firstname: "string",
			middlename: "string",
			lastname: "string",
			email: "string",
			phone_number: "string",
			company: "string",
			city: "string",
			country: "string",
			state_province: "string",
			address1: "string",
			address2: "string",
			zip_code: "string",
			latitude: double,
			longtitude: double,
		}
	},
]
```


# Customer order by id
#order
- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `/api/V1/customer/orders/{id}`

## Response data extends to [response format](response_format.md)
```js
{
		entity_id: number,
		increment_id: number,
		created_at: "DATE",
		expected_delivery_date: "DATE", // Optional
		status: "string",
		state: "string",
		total_amount: number,
		currency: "string",
		total_qty_ordered: number,
		items: [
			{
				product_id: number
				sku: number,
				media: "string",
			},
		],
		shipping_adress: {
			firstname: "string",
			middlename: "string",
			lastname: "string",
			email: "string",
			phone_number: "string",
			company: "string",
			city: "string",
			country: "string",
			state_province: "string",
			address1: "string",
			address2: "string",
			zip_code: "string",
			latitude: double,
			longtitude: double,
		}
	}
```




Invoice by Order ID	POST/api/V1/customer/orders/{id}/invoice
Customer shipment by Order ID	GET​/api​/V1​/customer​/orders​/{id}​/shipment
Refund request by Order ID	POST​/api​/V1​/customer​/orders​/{id}​/return
Cancelation request by Order ID	POST​/api​/V1​/customer​/orders​/{id}​/cancelation
Add a review for an order.	POST​/api​/V1​/customer​/orders​/{id}​/reviews





prescription by wed to be delivered
routific

update cart customer + add adreress objects. make it consistent 


docker run --name zeus -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=DEGjcDYBqH5k2GkY2T3MM43qWqwRMu -p 5432:5432 -d postgres                      