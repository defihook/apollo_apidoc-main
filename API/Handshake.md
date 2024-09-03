---
type: apidoc
project: hmg
area: node
module: handshake
owner: leanscale
reason: hmg-documentation
---

# Handshake API

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/handshake`

## Parameters
```
x-device-os-type  (string: ios | android | web)
x-app-version (string)
x-store (string: default | en) // or any store code i.e. "en"
```

## Request Body
```json
{}
```

## Response Body
```json
{
  "token": "string",
  "user": {
    "user_loggedIn": boolean,
    "store": "string",
    "refresh_token": "string",
  },
  "force_update": int,
  "feature_flags": {
    "enable_x": bool,
    "enable_y": bool
  }
}
```




# Refresh Handshake API

- From: E Pharmarcy Frontend
- To: Node API
- Method: `POST`
- API: `/api/V1/handshake/refresh`

## Parameters
```
x-device-os-type  (string: ios | android | web)
x-app-version (string)
x-store (string: default | en) // or any store code i.e. "en"
x-refresh-token (string)
```

## Request Body
```json
{}
```

## Response Body
```json
{
  "token": "string",
  "user": {
    "userLoggedIn": boolean,
    "store": "string",
    "refreshToken": "string",
  },
  "forceUpdate": int,
  "featureFlags": {
    "enableX": bool,
    "enableY": bool
  }
}
```
