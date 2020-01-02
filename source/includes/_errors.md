# Response Codes

<aside class="notice">
All status codes are standard HTTP status codes.
2XX - Success of some kind
4XX - Error occurred in client’s part
5XX - Error occurred in server’s part
</aside>

The Real Time Prices Service APIs use the following Status codes:


Status Code | Meaning
---------- | -------
200 | Valid. Returns {} if no results found.
202 | Accepted (Request accepted, and queued for execution)
400 | Bad request. Format is invalid.
401 | Authentication failure
403 | Forbidden. Invalid x-api-key.
404 | Resource not found
405 | Method Not Allowed
409 | Conflict
412 | Precondition Failed
413 | Request Entity Too Large
500 | Internal Server Error
501 | Not Implemented
503 | Service Unavailable
