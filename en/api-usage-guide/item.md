---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/item
---

# Item

### Game ➡️ Next Market

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/media/upload" method="post" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item" method="post" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/{sku}" method="put" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/{sku}" method="get" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item" method="get" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/ability" method="post" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/ability/{code}" method="put" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/ability" method="get" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

{% openapi-operation spec="api-fiddle-next-market-api-en" path="/api/v1/item/send-item/guid/{guid}" method="get" %}
[OpenAPI api-fiddle-next-market-api-en](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api-en)
{% endopenapi-operation %}

### Next Market ➡️ Game

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Item Delivery

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/send-item`

Provides functionality to request delivery to an account due to reasons such as user purchase or free distribution.

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

<table><thead><tr><th width="219.5872802734375">Parameter</th><th width="220.6856689453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>requestId</td><td>String <mark style="color:$danger;">*required</mark></td><td>If a request is made with the same identifier, it constitutes a duplicate request and must be returned with a code corresponding to a duplicate error.</td></tr><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>This is the account identifier defined by the game company. Since it may be exposed to unauthorized users through sharing between users, it must be an identifier that poses no issues regarding personal information handling.</td></tr><tr><td>referralCode</td><td>String</td><td><code>preview</code> Provides the referralCode if associated with the given GUID. The last updated value is transmitted when issuing a one-time token.</td></tr><tr><td>itemList</td><td>List&#x3C;Object> <mark style="color:$danger;">*required</mark></td><td>Specifies the list of items to be shipped. Since the shipment request is made for the quantity of simultaneous purchases, you must adjust the simultaneous purchase quantity at the time of sales registration.</td></tr><tr><td>itemList.sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>Specifies the SKU of the item to be shipped.</td></tr><tr><td>itemList.amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>Specifies the quantity of the item to be shipped.</td></tr><tr><td>payload</td><td>String</td><td><code>preview</code> The payload at the time of issuing the one-time token for the logged-in user's authentication is transmitted.</td></tr></tbody></table>

**Response**

You can define the details of each error according to the[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title="undefined" %}
```json
<Response body is empty.>
```
{% endtab %}
{% endtabs %}

#### Item Delivery Result

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/transaction`

Checks the processing status of the item requested for delivery. This API is for store management purposes, such as handling customer service inquiries. If the game company resolves the issue internally, this API need not be provided. It is not necessary to return all statuses; they can be defined based on the situation.

IN\_PROGRESS is defined as the point when the user becomes aware of the delivery item, and SUCCESS is defined as the point when the user becomes aware that the item has been used. If a mailbox system exists: - IN\_PROGRESS: Item has reached the mailbox. - SUCCESS: User has retrieved the item from the mailbox to their inventory. From a CS perspective, once an item reaches the SUCCESS state, the user is considered to have used it. Therefore, even if the item is refundable, refund processing is denied until the item is recovered.

```shellscript
curl -X POST {{endpoint}}/next-market/transaction?requestId=xxxxx-xxxxx-xxxxxx \
-H "Content-Type: application/json" 
```

**Headers**

| Name                                                                                   | Value                                                         |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json`                                            |
| <p>requestId <mark style="color:$danger;">*required</mark><br><em>(query)</em></p>     | This is the request identifier when requesting item delivery. |

**Body**

N/A

**Response**

<table><thead><tr><th width="220.4747314453125">Name</th><th width="219.9677734375">Type</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>String <mark style="color:$danger;">*required</mark></td><td><p>The status of the delivery request.<br></p><ul><li>PENDING: Pending</li><li>IN_PROGRESS: Received</li><li>SUCCESS: Delivery received</li><li>FAILED: Delivery failed</li></ul></td></tr></tbody></table>

**Response**

You can define the details of each error according to the[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with monitoring to recover or forcefully cancel the request.

{% tabs %}
{% tab title="200" %}
```json
{
  "status": "PENDING"
}
```
{% endtab %}
{% endtabs %}

#### Sealing

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/sealing`

This request excludes in-game items from sale by their owner. Sealed items must be in a state where ownership cannot be transferred or modified within the game, and ownership must be transferable at any time through sale.

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

<table><thead><tr><th width="219.82012939453125">Name</th><th width="220.44287109375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>The GUID of the item owner.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>The item code of the goods to be sealed.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that identifies the item to be sealed if it has unique attributes.</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>The quantity of the goods to be sealed.</td></tr><tr><td>c2cSaleId</td><td>Long <mark style="color:$danger;">*required</mark></td><td>The identification number of the registered C2C sale, which can be used by the game side when canceling the C2C.</td></tr></tbody></table>

**Response**

You can define the details of each error according to the[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title="undefined" %}
```
<Response body is empty.>
```
{% endtab %}
{% endtabs %}

#### Unsealing

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/unsealing`

This request unseals items previously sealed for sale, making them usable again in the game. It is used solely to return items to their original owners when a sale registration is canceled. Therefore, we recommend verifying the original owner when receiving this request. While sale registrations can be canceled by the owner, bulk or partial cancellations may also occur due to policy changes during operation or the game company's circumstances.<br>

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

<table><thead><tr><th width="220.32440185546875">Name</th><th width="220.4603271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>The GUID of the item owner.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>The item code of the sealed goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that identifies the item if the sealed goods have unique attributes.</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>The quantity of the sealed goods.</td></tr></tbody></table>

**Response**

You can define the details of each error according to the[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title="undefined" %}
```json
<Response body is empty.>
```
{% endtab %}
{% endtabs %}

#### Item Exchange

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/exchange`

This request processes the exchange of items purchased via C2C transactions for in-game currency. As this is a 1:1 exchange between seller and buyer, it is recommended to verify that the procedure for transferring the item from the seller's ownership to the buyer proceeds without issues.

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

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the user who made the purchase.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the purchasing user. For sessions without a presence input, a value of 0 is returned.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the selling user.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the selling user at the time of sale registration. If the presence is not entered during sale registration, a value of 0 is returned.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>The item code of the purchased goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that can identify the object if it has unique properties.</td></tr><tr><td>amount</td><td>Integer <mark style="color:red;">*required</mark></td><td>The quantity of purchased goods.</td></tr></tbody></table>

**Response**

You can define the details of each error according to the[Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title="undefined" %}
```json
<Response body is empty.>
```
{% endtab %}
{% endtabs %}

#### Item Exchange Verification

<mark style="color:green;">`POST`</mark>

`/next-market/verify`

Verifies whether the in-game currency is actually tradable before processing the exchange of items purchased by the user through C2C transactions.

```shellscript
curl -X POST {{endpoint}}/next-market/verify \
-H "Content-Type: application/json" \
-d '{
  "buyer": "buyer123-guid-xxxx",
  "buyerPresence": "server1-channelA",
  "seller": "seller456-guid-xxxx",
  "sellerPresence": "server2-channelB",
  "sku": "unique-armor-immortal",
  "serialNumber": "armor-serial-001",
  "c2cSaleId": 10
}'
```

**Headers**\
N/A

**Body**

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the user who made the purchase.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the purchasing user. For sessions without a presence input, a value of 0 is returned.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the selling user.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the selling user at the time of sale registration. If the presence is not entered during sale registration, a value of 0 is returned.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>The item code of the purchased goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that can identify the object if it has unique attributes.</td></tr><tr><td>c2cSaleId</td><td>Integer <mark style="color:red;">*required</mark></td><td>Sale ID registered for sale</td></tr></tbody></table>

\*\*Response\*\*

{% tabs %}
{% tab title="undefined" %}
```json
<Response body is empty.>
```
{% endtab %}
{% endtabs %}
