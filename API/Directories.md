---
type: apidoc
project: hmg
area: node
module: directories
owner: leanscale
reason: hmg-documentation
---


# Directories

## Get list of all pharmcies.
#cart

- From: E Pharmarcy Frontend
- To: Node API
- Method: `GET`
- API: `​/api​/V1​/directory​/pharmacies`

## Response data extends to [response format](response_format.md)
```js
{
  "entity_id": 1,
  "attribute_set_id": 12,
  "created_at": "2022-10-20 07:49:30",
  "updated_at": "2022-11-02 08:08:29",
  "organization_name": "Stuart and Houston LLC",
  "organization_code": "AMD",
  "sub_inventory_code": "4455",
  "city": "Abha",
  "phone": "+15944681907",
  "address": "Ut error perspiciati",
  "latitude": 10.2345,
  "longitude": 12.4353,
  "location": "sdf",
  "status": true,
  "is_fulfilment": true,
  "is_monday_open": true,
  "is_tuesday_open": false,
  "is_wednesday_open": false,
  "is_thursday_open": false,
  "is_friday_open": false,
  "is_saturday_open": false,
  "is_sunday_open": false,
  "alhabib_pharmacy_timezone_display": "Asia/Bahrain",
  "monday_start_time": "2022-10-20 09:16:00",
  "monday_end_time": "2022-10-20 23:59:00",
  "tuesday_start_time": "2022-10-20 00:00:00",
  "tuesday_end_time": "2022-10-20 23:59:00",
  "wednesday_start_time": "2022-10-20 00:00:00",
  "wednesday_end_time": "2022-10-20 23:59:00",
  "thursday_start_time": "2022-10-20 00:00:00",
  "thursday_end_time": "2022-10-20 23:59:00",
  "friday_start_time": "2022-10-20 00:00:00",
  "friday_end_time": "2022-10-20 23:59:00",
  "saturday_start_time": "2022-10-20 00:00:00",
  "saturday_end_time": "2022-10-20 23:59:00",
  "sunday_start_time": "2022-10-20 00:00:00",
  "sunday_end_time": "2022-10-20 23:59:00",
  "media": { // [TODO]
    "image": [
      {
        "original": "assetUrl",
        "position": number,
        "id": int,
        "alt_text": "string"
        "width": "string",
        "height": "string",
        "type": ["base"] // base || small || thumnail || swatch 
      }
    ]
    "video": [
      {
        "original": "https://m2-alpha.alhabibpharmacydev.com/media/alhabib/pharmacy/6/8/681023231-da34e34f89db49761936903f8e7564c151794a696433a6f6214620a9802f3d0c-d_640",
        "id": 2,
        "position": 2,
        "video_url": "https://vimeo.com/253989945",
        "video_title": "Sample Videost",
        "type": ["base"] // base || small || thumnail || swatch 
      }
    ]
  },
}
```
