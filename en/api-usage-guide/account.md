metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/account
---

# Account

## Next Market ➡️ Game

### Check Game Account Status

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/character-info`

Before a user enters the store with an authentication token or attempts delivery by purchasing an item, the game account status is queried to verify its validity and obtain basic information. Depending on the game&#x27;s structure, the acquired information—such as the characters owned by the account and the server they belong to—is displayed to the user to confirm their account ownership.

```bash
curl -X POST {{endpoint}}/next-market/character-info \
-H &quot;Content-Type: application/json&quot; \
-d &#x27;{
  &quot;guid&quot;: &quot;user123-guid-xxxx&quot;
}&#x27;
```

**Headers**

| Name                                                                                   | Value              |
| -------------------------------------------------------------------------------------- | ------------------ |
| <p>Content-Type <mark style="color:$danger;">*required</mark><br><em>(header)</em></p> | `application/json` |

**Body**

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>This is the identifier for the account defined by the game company. Since it may be exposed to unauthorized users through sharing between users, it must be an identifier that poses no issues regarding personal information handling.</td></tr></tbody></table>**Response**\
You can define the details for each error according to the [Error response format](error-response.md#error-response-format). If the store receives a 503 response, it will retry repeatedly. If it receives a 403, 406, or 500 response, it will proceed with monitoring to either recover or forcefully cancel the request.

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>signature</td><td>List&lt;String&gt; <mark style="color:$danger;">*required</mark></td><td>Returns the information held by the account as a string.<br>Example) Roel 10: Cat*ter This is<br>displayed directly to the user and serves as basic information provided to prevent confusion for users managing multiple accounts.</td></tr></tbody></table>{% tabs %}
{% tab title=&quot;200&quot; %}
```json
{
  &quot;signature&quot;: [
    &quot;Rael 10: Gyeok€€sa&quot;,
    &quot;Server: Artiria&quot;,
    &quot;Level: 85&quot;
  ]
}
```
{% endtab %}
{% endtabs %}
