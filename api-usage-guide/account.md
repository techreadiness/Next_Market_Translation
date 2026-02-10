---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/account
---

# 계정

## Next Market ➡️ Game

### 게임 계정 상태 조회

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/character-info`

사용자가 인증토큰으로 스토어에 진입하거나 상품 구매에 의해 배송을 시도하기전 게임 계정의 정상성을 확인하기 위해 상태를 조회하며 기본적인 정보를 입수합니다. 게임의 구조에 따라 계정이 보유중인 캐릭터와 소속 서버의 정보등을 통해 사용자는 본인의 계정임을 인지할 수 있도록 습득한 정보를 사용자에게 게시합니다.

```bash
curl -X POST {{endpoint}}/next-market/character-info \
-H "Content-Type: application/json" \
-d '{
  "guid": "user123-guid-xxxx"
}'
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>게임사 측에서 정의한 계정의 식별자입니다. 사용자간 공유를 통해 비인가된 사용자에게도 노출될 가능성이 있으므로 개인정보 취급상에 문제가 없는 식별자가 되어야 합니다.</td></tr></tbody></table>

**Response**\
[Error response format](error-response.md#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 403, 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>signature</td><td>List&#x3C;String> <mark style="color:$danger;">*required</mark></td><td>계정이 보유한 정보를 문자열로 반환합니다.<br>예시) 로엘 10: 캐*터<br>사용자에게 직접 노출되며 다수의 계정을 사용하는 사용자에게 혼란이 없도록 제공하는 기본정보로서 표현됩니다.</td></tr></tbody></table>

{% tabs %}
{% tab title="200" %}
```json
{
  "signature": [
    "라엘 10: 격€€사",
    "서버: 아르티리아",
    "레벨: 85"
  ]
}
```
{% endtab %}
{% endtabs %}

