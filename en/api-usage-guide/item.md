metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/item
---

# Item

## Game ➡️ Next Market

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/media/upload&quot; method=&quot;post&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item&quot; method=&quot;post&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/{sku}&quot; method=&quot;put&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/{sku}&quot; method=&quot;get&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item&quot; method=&quot;get&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/ability&quot; method=&quot;post&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/ability/{code}&quot; method=&quot;put&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/ability&quot; method=&quot;get&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

{% openapi-operation spec=&quot;fiddle-next-market-api&quot; path=&quot;/api/v1/item/send-item/guid/{guid}&quot; method=&quot;get&quot; %}
[OpenAPI fiddle-next-market-api](https://api.api-fiddle.com/v1/public/resources/oas_api_3_1/techreadinesss-organization-px3/next-market-api)
{% endopenapi-operation %}

## Next Market ➡️ Game

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>### Item Delivery

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/send-item` 

Provides functionality to request delivery to an account for reasons such as user purchase or free distribution.

```bash
curl -X POST {{endpoint}}/next-market/send-item \
-H &quot;Content-Type: application/json&quot; \
-d &#x27;{
  &quot;requestId&quot;: &quot;delivery-req-2025-001&quot;,
  &quot;guid&quot;: &quot;user123-guid-xxxx&quot;,
  &quot;referralCode&quot;: &quot;INFLUENCER123&quot;,
  &quot;itemList&quot;: [
    {
      &quot;sku&quot;: &quot;unique-armor-immortal&quot;,
      &quot;amount&quot;: 1
    },
    {
      &quot;sku&quot;: &quot;health-potion-large&quot;,
      &quot;amount&quot;: 5
    }
  ],
  &quot;payload&quot;: &quot;server:arteria,level:85,class:warrior&quot;
}&#x27;
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

<table><thead><tr><th width="219.5872802734375">Parameter</th><th width="220.6856689453125">Type</th><th>Description</th></tr></thead><tbody><tr><td>requestId</td><td>String <mark style="color:$danger;">*required</mark></td><td>If a request is made with the same identifier, it constitutes a duplicate request and must be returned with a code corresponding to a duplicate error.</td></tr><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>This is the account identifier defined by the game company. Since it may be exposed to unauthorized users through sharing between users, it must be an identifier that poses no issues regarding personal information handling.</td></tr><tr><td>referralCode</td><td>String</td><td><code>preview</code> Provides the referralCode if associated with the given GUID. The last updated value is transmitted when issuing a one-time token.</td></tr><tr><td>itemList</td><td>List&lt;Object&gt; <mark style="color:$danger;">*required</mark></td><td>Specifies the list of items to be delivered. Since delivery is requested for the quantity of simultaneous purchases, you must adjust the simultaneous purchase quantity at the time of sales registration.</td></tr><tr><td>itemList.sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>Specifies the SKU of the item to be shipped.</td></tr><tr><td>itemList.amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>Specifies the quantity of items to be shipped.</td></tr><tr><td>payload</td><td>String</td><td><code>preview</code> The payload at the time of issuing the one-time token for the logged-in user&#x27;s authentication is transmitted.</td></tr></tbody></table>**Response**

You can define the details of each error according to the [Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title=&quot;200&quot; %}
```json
&lt;The response body is empty.&gt;
```
{% endtab %}
{% endtabs %}

### Item Delivery Result

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/transaction`

Checks the processing status of the item requested for delivery. This API is for store management purposes, such as handling customer service inquiries. If the game company resolves the issue internally, this API need not be provided. It is not necessary to return all statuses; they can be defined based on the situation.

IN_PROGRESS is defined as the point when the user becomes aware of the delivery item, and SUCCESS is defined as the point when the user recognizes they have used the item. If a mailbox system exists, IN_PROGRESS applies when the item reaches the mailbox, and SUCCESS applies when the user retrieves it from the mailbox to their inventory. From a CS perspective, if the status is SUCCESS, the user is considered to have used the item. Therefore, even if the item is refundable, refund processing is denied until it is retrieved.

```shellscript
curl -X POST {{endpoint}}/next-market/transaction?requestId=xxxxx-xxxxx-xxxxxx \
-H &quot;Content-Type: application/json&quot; 
```

**Headers**

| Name                                                                                   | Value                 |
| -------------------------------------------------------------------------------------- | --------------------- |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json`    |
| <p>requestId <mark style="color:$danger;">*required</mark><br><em>(query)</em></p>     | This is the request identifier when requesting item delivery. |

**Body**

N/A

**Response**

<table><thead><tr><th width="220.4747314453125">Name</th><th width="219.9677734375">Type</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>String <mark style="color:$danger;">*required</mark></td><td><p>The status of the delivery request.<br></p><ul><li>PENDING: Pending</li><li>IN_PROGRESS: Received</li><li>SUCCESS: Delivery received</li><li>FAILED: Delivery failed</li></ul></td></tr></tbody></table>**Response**\
You can define the details for each error according to the [Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with monitoring to either recover or forcefully cancel the request.

{% tabs %}
{% tab title=&quot;200&quot; %}
```json
{
  &quot;status&quot;: &quot;PENDING&quot;
}
```
{% endtab %}
{% endtabs %}

### Sealing

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/sealing`

This request excludes in-game assets from sale by their owner. Sealed assets must be in a state where ownership transfer or modification is impossible within the game, and ownership must be transferable at any time through sale.

```shellscript
curl -X POST {{endpoint}}/next-market/sealing \
-H &quot;Content-Type: application/json&quot; 
-d &#x27;{ &quot;guid&quot;: &quot;xxxx&quot;, &quot;sku&quot;: &quot;xxxx&quot;, &quot;serialNumber&quot;: &quot;xxxx&quot;, &quot;amount&quot;: 1 }&#x27;
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="219.82012939453125">Name</th><th width="220.44287109375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>The GUID of the item owner.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>The item code of the goods to be sealed.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that identifies the item to be sealed if it has unique properties.</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>The quantity of the goods to be sealed.</td></tr><tr><td>c2cSaleId</td><td>Long <mark style="color:$danger;">*required</mark></td><td>The registered identification number for the C2C sale. This can be used by the game side when canceling a C2C transaction.</td></tr></tbody></table>**Response**\
You can define the details of each error according to the [Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with recovery or force cancellation of the request through monitoring.

{% tabs %}
{% tab title=&quot;200&quot; %}
```
&lt;Response body is empty.&gt;
```
{% endtab %}
{% endtabs %}

### Unsealing

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/unsealing`

This request unseals an item previously sealed for sale, making it usable again in the game. It is intended solely for returning items to their original owners when a sale registration is canceled. Therefore, it is recommended to verify the original owner when receiving this request. Items listed for sale may be canceled by the owner, but they can also be canceled in bulk or partially due to policy changes during operation or circumstances on the game company&#x27;s side.

<br>

```shellscript
curl -X POST {{endpoint}}/next-market/unsealing \
-H &quot;Content-Type: application/json&quot; 
-d &#x27;{ &quot;guid&quot;: &quot;xxxx&quot;, &quot;sku&quot;: &quot;xxxx&quot;, &quot;serialNumber&quot;: &quot;xxxx&quot;, &quot;amount&quot;: 1 }&#x27;
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="220.32440185546875">Name</th><th width="220.4603271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>The GUID of the item owner.</td></tr><tr><td>sku</td><td>String <mark style="color:$danger;">*required</mark></td><td>The item code of the sealed goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that identifies the item if the sealed goods have unique attributes.</td></tr><tr><td>amount</td><td>Integer <mark style="color:$danger;">*required</mark></td><td>The quantity of the sealed goods.</td></tr></tbody></table>**Response**\
You can define the details of each error according to the [Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with monitoring to recover or forcefully cancel the request.

{% tabs %}
{% tab title=&quot;200&quot; %}
```json
&lt;Response body is empty.&gt;
```
{% endtab %}
{% endtabs %}

### Item Exchange

`preview` `prod`

<mark style="color:green;">`POST`</mark>

`/next-market/exchange`

This request processes the exchange of items purchased via C2C transactions into in-game currency. As this is a 1:1 exchange between seller and buyer, it is recommended to verify that the procedure for transferring the item from the seller to the buyer proceeds without issues.

```shellscript
curl -X POST {{endpoint}}/next-market/exchange \
-H &quot;Content-Type: application/json&quot; \
-d &#x27;{
  &quot;buyer&quot;: &quot;buyer123-guid-xxxx&quot;,
  &quot;buyerPresence&quot;: &quot;Server1-ChannelA&quot;,
  &quot;seller&quot;: &quot;seller456-guid-xxxx&quot;,
  &quot;sellerPresence&quot;: &quot;server2-channelB&quot;,
  &quot;sku&quot;: &quot;unique-armor-immortal&quot;,
  &quot;serialNumber&quot;: &quot;armor-serial-001&quot;,
  &quot;amount&quot;: 1
}&#x27;
```

**Headers**\
N/A

**Body**

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the user who made the purchase.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the purchasing user. For sessions without a presence input, a value of 0 is returned.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the selling user.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the selling user at the time of sale registration. If the presence is not entered during sale registration, a value of 0 is returned.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>The item code of the purchased goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that can identify the object if it has unique properties.</td></tr><tr><td>amount</td><td>Integer <mark style="color:red;">*required</mark></td><td>The quantity of purchased goods.</td></tr></tbody></table>**Response**\
You can define the details of each error according to the [Error response format](/broken/pages/feLd98hbmw2Uop5UV373#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 406 or 500 response, it will proceed with monitoring to either recover or forcefully cancel the request.

{% tabs %}
{% tab title=&quot;200&quot; %}
```json
&lt;Response body is empty.&gt;
```
{% endtab %}
{% endtabs %}

### Item Exchange Verification

<mark style="color:green;">`POST`</mark>

`/next-market/verify`

Verifies whether the currency is actually tradable before processing the exchange of items purchased via C2C transactions into in-game currency.

```shellscript
curl -X POST {{endpoint}}/next-market/verify \
-H &quot;Content-Type: application/json&quot; \
-d &#x27;{
  &quot;buyer&quot;: &quot;buyer123-guid-xxxx&quot;,
  &quot;buyerPresence&quot;: &quot;Server1-ChannelA&quot;,
  &quot;seller&quot;: &quot;seller456-guid-xxxx&quot;,
  &quot;sellerPresence&quot;: &quot;Server2-ChannelB&quot;,
  &quot;sku&quot;: &quot;unique-armor-immortal&quot;,
  &quot;serialNumber&quot;: &quot;armor-serial-001&quot;,
  &quot;c2cSaleId&quot;: 10
}&#x27;
```

**Headers**\
N/A

**Body**

<table><thead><tr><th width="220.2430419921875">Parameter</th><th width="220.289306640625">Type</th><th>Description</th></tr></thead><tbody><tr><td>buyer</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the user who made the purchase.</td></tr><tr><td>buyerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the purchasing user. For sessions without a presence input, a value of 0 is returned.</td></tr><tr><td>seller</td><td>String <mark style="color:red;">*required</mark></td><td>The GUID of the selling user.</td></tr><tr><td>sellerPresence</td><td>String <mark style="color:red;">*required</mark></td><td>The authentication presence value of the selling user at the time of sale registration. If the presence is not entered during sale registration, a value of 0 is returned.</td></tr><tr><td>sku</td><td>String <mark style="color:red;">*required</mark></td><td>The item code of the purchased goods.</td></tr><tr><td>serialNumber</td><td>String</td><td>A number or code that identifies the object when it has unique attributes.</td></tr><tr><td>c2cSaleId</td><td>Integer <mark style="color:red;">*required</mark></td><td>Sale ID registered for sale</td></tr></tbody></table>**Response**

{% tabs %}
{% tab title=&quot;200&quot; %}
```json
&lt;Response body is empty.&gt;
```
{% endtab %}
{% endtabs %}
