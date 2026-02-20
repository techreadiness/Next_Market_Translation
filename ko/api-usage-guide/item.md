---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/item
---

# 아이템

## Game ➡️ Next Market

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/media/upload" method="post" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item" method="post" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/{sku}" method="put" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/{sku}" method="get" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item" method="get" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/ability" method="post" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/ability/{code}" method="put" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/ability" method="get" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec="fiddle-next-market-api" path="/api/v1/item/send-item/guid/{guid}" method="get" %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

## Next Market ➡️ Game

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### 아이템 배송

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/send-item`&#x20;

사용자 구매나 무료 지급등의 사유로 계정에게 배송을 요청하는 기능을 제공합니다.

```bash
curl -X POST {{endpoint}}/next-market/send-item \
-H "Content-Type: application/json" \
-d '{
  "requestId": "delivery-req-2025-001",
  "guid": "user123-guid-xxxx",
  "referralCode": "INFLUENCER123",
  "itemList": [
    {
      "sku": "unique-armor-immortal",
      "amount": 1
    },
    {
      "sku": "health-potion-large",
      "amount": 5
    }
  ],
  "payload": "server:arteria,level:85,class:warrior"
}'
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

<table><thead><tr><th width="219.5872802734375">Parameter</th><th width="220.6856689453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>requestId</td><td>String <mark style="color:$danger;">*required</mark></td><td>동일한 식별자로 요청이 되는 경우 중복 요청에 해당하므로 중복 오류에 해당하는 코드로 반환되어야 합니다.</td></tr><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>게임사 측에서 정의한 계정의 식별자입니다. 사용자간 공유를 통해 비인가된 사용자에게도 노출될 가능성이 있으므로 개인정보 취급상에 문제가 없는 식별자가 되어야 합니다.</td></tr><tr><td>referralCode</td><td>String</td><td><code>preview</code> 해당 guid에 referralCode가 있다면 제공합니다. 원타임 토큰 발급 시에 마지막으로 갱신된 값이 전달됩니다.</td></tr><tr><td>itemList</td><td>List&#x3C;Object> <mark style="color:$danger;">*required</mark></td><td>배송 받을 아이템 목록을 지정합니다. 동시 구매 수량만큼 배송 요청되므로 판매 등록 시점에 동시 구매수량을 조절하셔야 합니다.</td></tr><tr><td>itemList.sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>배송 받을 아이템의 품목코드를 지정합니다.</td></tr><tr><td>itemList.amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>배송 받을 아이템의 수량을 지정합니다.</td></tr><tr><td>payload</td><td>String</td><td><code>preview</code> 로그인한 사용자의 인증용 원타임 토큰 발행 시점의 payload가 전달됩니다.</td></tr></tbody></table>

**Response**

[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

{% tabs %}
{% tab title="200" %}
```json
<응답 본문이 비어있습니다.>
```
{% endtab %}
{% endtabs %}

### 아이템 배송 결과

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/transaction`

배송 요청한 아이템의 처리 상태를 조회합니다. 스토어측에서 CS 대응 문의 등을 위한 관리용도의 API이며 게임사 측 자체 대응으로 문제를 해소한다면 해당 API는 제공하지 않아도 됩니다. 모든 상태를 반환할 필요가 없으며 상황에 따라 정의할 수 있습니다.

IN\_PROGRESS는 사용자가 배송 아이템을 인지하는 시점이고 SUCCESS는 사용자가 아이템을 사용하였음을 인지한 시점으로 기준을 정의합니다. 우편함 시스템이 있는 경우 우편함에 도달했다면 IN\_PROGRESS, 사용자가 우편함으로부터 자신의 인벤토리로 수취했다면 SUCCESS가 됩니다. CS 기준으로 SUCCESS 상태이면 사용자가 아이템을 사용했다고 인지하여 환불가능한 아이템이더라도 회수 전까지 환불처리를 거부합니다.

```shellscript
curl -X POST {{endpoint}}/next-market/transaction?requestId=xxxxx-xxxxx-xxxxxx \
-H "Content-Type: application/json" 
```

**Headers**

| Name                                                                                   | Value                 |
| -------------------------------------------------------------------------------------- | --------------------- |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json`    |
| <p>requestId <mark style="color:$danger;">*required</mark><br><em>(query)</em></p>     | 아이템 배송 요청시에 요청식별자입니다. |

**Body**

N/A

**Response**

<table><thead><tr><th width="220.4747314453125">Name</th><th width="219.9677734375">Type</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>String <mark style="color:$danger;">*required</mark></td><td><p>배송 요청의 상태.<br></p><ul><li>PENDING: 대기중</li><li>IN_PROGRESS: 배송 받음</li><li>SUCCESS: 배송 수취</li><li>FAILED: 배송 실패</li></ul></td></tr></tbody></table>

**Response**\
[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

{% tabs %}
{% tab title="200" %}
```json
{
  "status": "PENDING"
}
```
{% endtab %}
{% endtabs %}

### 실링

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/sealing`

게임내 재화를 소유자로부터 판매를 위해 제외시키는 요청입니다. 실링한 재화는 게임 안에서 소유권 이전이나 변형을 할 수 없는 상태여야 하며 판매를 통해 소유권이 언제든 이전될 수 있어야 합니다.

```shellscript
curl -X POST {{endpoint}}/next-market/sealing \
-H "Content-Type: application/json" 
-d '{ "guid": "xxxx", "sku": "xxxx", "serialNumber": "xxxx", "amount": 1 }'
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="219.82012939453125">Name</th><th width="220.44287109375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>재화 소유자의 guid 입니다.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>실링할 재화의 품목코드 입니다.</td></tr><tr><td>serialNumber</td><td>String</td><td>실링할 재화가 고유속성을 가진 경우 대상을 식별할 수 있는 번호 또는 코드 입니다.</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>실링할 재화의 수량입니다.</td></tr><tr><td>c2cSaleId</td><td>Long <mark style="color:$danger;">*required</mark></td><td>C2C 판매 등록된 식별 번호로 게임측에서 C2C 취소할 때 사용할 수 있습니다.</td></tr></tbody></table>

**Response**\
[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

{% tabs %}
{% tab title="200" %}
```
<응답 본문이 비어있습니다.>
```
{% endtab %}
{% endtabs %}

### 언실링

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/unsealing`

판매를 위해 실링했던 아이템을 다시 게임에서 사용할 수 있도록 해제하는 요청입니다. 스토어에 판매 등록했던 아이템의 등록이 취소되는 경우에 원 소유주에게 되돌려 주기 위한 목적으로만 사용하므로 요청을 받았을 때 원 소유주 여부를 검증하는 것을 권장합니다. 판매 등록한 아이템은 소유주에 의해 취소되기도 하지만 운영중 정책 변경이나 게임사의 사정에 의해 일괄 또는 부분 취소가 이루어질 수 있습니다.<br>

```shellscript
curl -X POST {{endpoint}}/next-market/unsealing \
-H "Content-Type: application/json" 
-d '{ "guid": "xxxx", "sku": "xxxx", "serialNumber": "xxxx", "amount": 1 }'
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="220.32440185546875">Name</th><th width="220.4603271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>재화 소유자의 guid 입니다.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>실링했던 재화의 품목코드 입니다.</td></tr><tr><td>serialNumber</td><td>String</td><td>실링했던 재화가 고유속성을 가진 경우 대상을 식별할 수 있는 번호 또는 코드</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>실링했던 재화의 수량입니다.</td></tr></tbody></table>

**Response**\
[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

{% tabs %}
{% tab title="200" %}
```json
<응답 본문이 비어있습니다.>
```
{% endtab %}
{% endtabs %}

### 아이템 교환

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/exchange`

사용자가 C2C 거래를 통해 구매한 아이템을 게임내 재화로 교환처리하기 위한 요청입니다. 판매자와 구매자간의 1:1 교환이므로 판매자 소유였던 항목이 구매자에게 인계되는 절차상 문제가 없는지 검증하는 것을 권장합니다.

```shellscript
curl -X POST {{endpoint}}/next-market/exchange \
-H "Content-Type: application/json" \
-d '{
  "buyer": "buyer123-guid-xxxx",
  "buyerPresence": "서버1-채널A",
  "seller": "seller456-guid-xxxx",
  "sellerPresence": "서버2-채널B",
  "sku": "unique-armor-immortal",
  "serialNumber": "armor-serial-001",
  "amount": 1
}'
```

**Headers**\
N/A

**Body**

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>구매한 사용자의 guid 입니다.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>구매 사용자의 인증 presence 값입니다. presence 미입력 세션의 경우 0값이 반환됩니다.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>판매한 사용자의 guid 입니다.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>판매 사용자의 판매등록시 인증 presence 값입니다. 판매등록시 presence 미입력 세션의 경우 0값이 반환됩니다.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>구매한 재화의 품목코드 입니다.</td></tr><tr><td>serialNumber</td><td>String</td><td>고유속성을 가진 경우 대상을 식별할 수 있는 번호 또는 코드</td></tr><tr><td>amount</td><td>Integer <mark style="color:red;">*required</mark></td><td>구매한 재화의 수량입니다.</td></tr></tbody></table>

**Response**\
[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format)에 맞춰 각 오류의 상세를 자체 정의할 수 있습니다. 스토어 측에서는 503 응답을 받은 경우 재시도를 반복하게 되며 406, 500의 응답을 받는 경우 모니터링을 통해 복구 또는 요청을 강제 취소하는 절차를 진행하게 됩니다.

{% tabs %}
{% tab title="200" %}
```json
<응답 본문이 비어있습니다.>
```
{% endtab %}
{% endtabs %}

### 아이템 교환 검증

<mark style="color:green;">`POST`</mark> `/next-market/verify`

사용자가 C2C 거래를 통해 구매한 아이템을 게임내 재화로 교환처리하기전에 실제로 재화가 거래가능한 상태인지 검증합니다.

```shellscript
curl -X POST {{endpoint}}/next-market/verify \
-H "Content-Type: application/json" \
-d '{
  "buyer": "buyer123-guid-xxxx",
  "buyerPresence": "서버1-채널A",
  "seller": "seller456-guid-xxxx",
  "sellerPresence": "서버2-채널B",
  "sku": "unique-armor-immortal",
  "serialNumber": "armor-serial-001",
  "c2cSaleId": 10
}'
```

**Headers**\
N/A

**Body**

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>구매한 사용자의 guid 입니다.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>구매 사용자의 인증 presence 값입니다. presence 미입력 세션의 경우 0값이 반환됩니다.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>판매한 사용자의 guid 입니다.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>판매 사용자의 판매등록시 인증 presence 값입니다. 판매등록시 presence 미입력 세션의 경우 0값이 반환됩니다.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>구매한 재화의 품목코드 입니다.</td></tr><tr><td>serialNumber</td><td>String</td><td>고유속성을 가진 경우 대상을 식별할 수 있는 번호 또는 코드</td></tr><tr><td>c2cSaleId</td><td>Integer <mark style="color:red;">*required</mark></td><td>판매등록한 saleId</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
<응답 본문이 비어있습니다.>
```
{% endtab %}
{% endtabs %}
