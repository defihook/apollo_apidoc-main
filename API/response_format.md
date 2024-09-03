---
type: apidoc
project: hmg
area: node
module: formatting
owner: leanscale
reason: hmg-documentation
---


# Response Format

| Type    | Description                                                                                         | Required Keys   | Optional Keys |
| ------- | --------------------------------------------------------------------------------------------------- | --------------- | ------------- |
| success | All went well, and (usually) some data was returned.                                                | status, data    |               |
| fail    | There was a problem with the data submitted, or some pre-condition of the API call wasn't satisfied | status, errors  |               |
| error   | An error occurred in processing the request, i.e. an exception was thrown                           | status, message | code, data    |



## Success Response
When an API call is successful, the object is used as a simple envelope for the results, using the data key

```json
{
    "status": "success", // status: Should always be set to "success".
    "data": { }
}
```


## Fail Response
When an API call is rejected due to invalid data or call conditions, the object's data key contains an object explaining what went wrong at which domain with a reason and message

```json
{
    "status" : "fail", // status: Should always be set to "success".
    "errors": [
            {
                // Unique identifier for the service raising this error. This helps distinguish service-specific errors (i.e. error inserting an event in a calendar) from general protocol errors (i.e. file not found).
                "domain": "string",
                // Unique identifier for this error. Different from the error.code property in that this is not an http response code.
                "reason": "string",
                // A human readable message providing more details about the error. If there is only one error, this field will match error.message.
                "message": "string"
            }
        ]
}
```


## Error
When an API call fails due to an error on the server.

```json
{
    "status" : "error", 
    "message" : "Unable to communicate with database"
}
```

