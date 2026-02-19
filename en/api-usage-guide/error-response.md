metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/error-response
---

# Error Responses

### Regular Error Response

API requests return either 4xx client-side errors or 4xx server-side errors. Server-side errors due to status or configuration issues return 500, while logical errors in client-side input return 406. If a 500 error is returned, retrying after server normalization or configuration changes is possible; therefore, the detailed error code must be checked and appropriate action taken. If a 406 error is returned, the input cannot be processed normally; thus, the detailed error code must be checked and the input adjusted. For other general HTTP communication errors, modify the request method according to the corresponding HTTP Status description or report the issue.

For errors specific to particular APIs, please refer to the error codes in the API documentation.

| HTTP Status | HTTP Code                                             | Description                                                                     |
| ----------- | ----------------------------------------------------- | ------------------------------------------------------------------------------- |
| 500         | [Error Code](error-response.md#error-response-format) | Server-side status error. Check the detailed response code.                                           |
| 503         | SERVICE\_UNAVAILABLE                                  | An abnormal response is returned due to an error in server-side infrastructure configuration. Wait for recovery when this occurs. Also occurs during system maintenance. |
| 400         | BAD_REQUEST                                          | There is an issue with the format or length of the input parameters. Please recheck the input parameters.                              |
| 403         | NOT_ALLOW_API                                       | Unauthorized API path                                                                |
| 406         | [Error Code](error-response.md#error-response-format) | The input request cannot be processed. Please check the detailed response code.                                      |
| 401         | UNAUTHORIZED                                          | The API Key or Secret is incorrect, or permissions have been revoked.                                          |
| 404         | NOT_FOUND                                            | An incorrect URI was specified.                                                                |
| 405         |                                                       | An unsupported HTTP Method was specified.                                                    |
| 406         | NOT\_ACCEPTABLE                                       |                                                                                 |
| 429         |                                                       | The request count has been exceeded due to too many requests.                                                       |

### Error Response Format

For HTTP Status 500 and 406, the response body always returns the detailed error code in the following format as `code` and `message`.

```json
{
  &quot;code&quot;: &quot;INVALID_APP_CREDENTIAL&quot;,
  &quot;message&quot;: &quot;App id &amp; secret is not valid&quot;
}
```

### Retryable Error Response

A 500 error response is returned when a temporary state error occurs, allowing for retries, or when specific data settings are not linked, requiring a retry after data configuration even though the request itself is valid. If a 500 error response is returned, the development team can request changes from us if monitoring indicates it requires action.

| code                    | message                            | description                                     |
| ----------------------- | ---------------------------------- | ----------------------------------------------- |
| INTERNAL\_SERVER\_ERROR | \{{Error Message\}}                | Error due to abnormal server state, making processing impossible for some or all requests. |
| MAINTENANCE             | Maintenance                        | Temporary/scheduled maintenance status.                                 |
| ILLEGAL_STATE          | Illegal state: \{{Error Message\}} | When the request cannot be processed temporarily due to a state change or request block.     |

### Non Retryable Error Response

A 406 error response is returned when the issue lies with client-side input, and the error cannot be resolved with the same input parameters.

httpStatus : 406

| code                                               | message                          | description                      |
| -------------------------------------------------- | -------------------------------- | -------------------------------- |
| BAD\_REQUEST                                       | Bad request                      | All cases where request parameters contain errors            |
| NOT\_FOUND                                         | Not found                        | When the requested target does not exist                |
| CONFLICT                                           | Already exists                   | When duplicate change requests are made                 |
| NOT_ENOUGH_ASSET                                 | Not enough asset                 | When the requested asset is insufficient or requested in an incorrect quantity |
| NEXT_MARKET_NOT_REGISTERED_GAME_ITEM_PACKAGE | Not registered game item package | When attempting to include an unregistered item in a package     |
