---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/error-response
---

# 에러 응답

### Regular Error Response

API요청 시 4xx 의 요청측 오류와 4xx 의 서버측 오류로 나눠지며 서버측 상태나 설정 등에 의한 오류는 500, 클라이언트측 입력상의 논리적 오류는 406로 반환됩니다. 500으로 반환되는 경우 서버측 정상화나 설정 변경 등을 통해 재시도가 가능하므로 세부 오류 코드를 확인해 조치를 취해야 하며 406로 반환되는 경우 동일 입력으로는 정상 수행이 불가한 항목이므로 세부 오류 코드를 확인하여 입력 사항을 조정해야 합니다. 그외 HTTP 통신상 일반적인 오류는 HTTP Status에 해당하는 설명에 따라 요청 방식을 변경하거나 제보가 필요합니다.

특정 API에 특화된 오류는 API 문서 상에 오류코드를 참조해 주세요.

| HTTP Status | HTTP Code                                             | Description                                                                     |
| ----------- | ----------------------------------------------------- | ------------------------------------------------------------------------------- |
| 500         | [Error Code](error-response.md#error-response-format) | 서버측 상태 이상 오류입니다. 상세 정의된 응답 코드를 확인하세요.                                           |
| 503         | SERVICE\_UNAVAILABLE                                  | 서버측 인프라 구성상의 오류로 인해 비정상적인 응답을 반환하는 상황이므로 발생시 복구까지 대기가 필요합니다. 시스템 점검인 경우에도 발생합니다 |
| 400         | BAD\_REQUEST                                          | 입력 파라미터의 형식이나 길이 등에 문제가 있습니다. 입력 파라미터를 다시 확인해 주세요.                              |
| 403         | NOT\_ALLOW\_API                                       | 허용되지 않는 api Path                                                                |
| 406         | [Error Code](error-response.md#error-response-format) | 입력상 처리될 수 없는 요청인 경우이며 상세 정의된 응답 코드를 확인하세요.                                      |
| 401         | UNAUTHORIZED                                          | API Key 또는 Secret이 잘못되었거나 권한이 회수되었습니다.                                          |
| 404         | NOT\_FOUND                                            | 잘못된 URI를 지정했습니다.                                                                |
| 405         |                                                       | 지원하지 않는 HTTP Method를 지정했습니다.                                                    |
| 406         | NOT\_ACCEPTABLE                                       |                                                                                 |
| 429         |                                                       | 너무 많은 요청에 의해 요청수를 초과했습니다.                                                       |

### &#x20;Error Response Format&#x20;

HTTP Status 500, 406에서는 항상 응답 본문에 code와 message로 상세 오류 코드를 다음과 같은 형식으로 반환합니다.

```json
{
  "code": "INVALID_APP_CREDENTIAL,
  "message": "App id & secret is not valid"
}
```

### Retryable Error Response

일시적인 상태 오류가 발생하여 재시도를 할 수 있는 상태이거나 특정 데이터 설정이 연계되어 있지 않아 정상적인 요청임에도 데이터 설정 후에 재시도가 필요한 사항인 경우에 500의 에러 응답을 반환합니다. 500 오류 응답을 반환하는 경우 개발팀이 모니터링을 통해 인지하여 조치가 필요한 사항인 경우 당사에 변경을 요청할 수 있습니다.

| code                    | message                            | description                                     |
| ----------------------- | ---------------------------------- | ----------------------------------------------- |
| INTERNAL\_SERVER\_ERROR | \{{Error Message\}}                | 서버 상태 이상에 의한 오류로 일부 또는 전체 요청에 대해 처리가 불가한 상태인 경우 |
| MAINTENANCE             | Maintenance                        | 임시/정기 점검 상태인 경우                                 |
| ILLEGAL\_STATE          | Illegal state: \{{Error Message\}} | 상태 변경이나 요청 블록에 의해 일시적으로 요청을 처리할 수 없는 상태인 경우     |

### Non Retryable Error Response

클라이언트 측 입력상의 문제가 있어 동일한 입력 파라미터로는 오류 해소가 불가능한 경우에 406의 에러 응답을 반환합니다.

httpStatus : 406

| code                                               | message                          | description                      |
| -------------------------------------------------- | -------------------------------- | -------------------------------- |
| BAD\_REQUEST                                       | Bad request                      | 요청 파라미터에 오류가 있는 모든 경우            |
| NOT\_FOUND                                         | Not found                        | 요청 대상이 존재하지 않는 경우                |
| CONFLICT                                           | Already exists                   | 중복으로 변경 요청이 된 경우                 |
| NOT\_ENOUGH\_ASSET                                 | Not enough asset                 | 요청 대상의 자산이 부족하거나 잘못된 수량으로 요청된 경우 |
| NEXT\_MARKET\_NOT\_REGISTERED\_GAME\_ITEM\_PACKAGE | Not registered game item package | 등록되지 않은 아이템을 패키지에 포함하려고 시도한 경우   |
