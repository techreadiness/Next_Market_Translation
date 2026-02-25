---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/account
---

# Account

## Next Market ➡️ Game

### Game Account Status Inquiry

`preview` `prod`

<mark style="color:green;">`POST`</mark> `/next-market/character-info`

Before a user enters the store using an authentication token or attempts delivery by purchasing an item, the system checks the status to verify the game account's validity and obtains basic information. Based on the game's structure, the system displays the acquired information to the user—such as the characters owned by the account and the server they belong to—so the user can recognize it as their own account.

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

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>guid</td><td>String <mark style="color:$danger;">*required</mark></td><td>This is the account identifier defined by the game company. Since it may be exposed to unauthorized users through sharing between users, it must be an identifier that poses no issues regarding personal information handling.</td></tr></tbody></table>

**Response**

&#x20;You can define the details of each error according to the [Error response format](error-response.md).

If the store receives a 503 response, it will retry repeatedly. If it receives a 403, 406, or 500 response, it will proceed with monitoring to either recover or forcefully cancel the request.

<table><thead><tr><th width="219.88970947265625">Field</th><th width="219.6478271484375">Type</th><th>Description</th></tr></thead><tbody><tr><td>signature</td><td>List&#x3C;String> <mark style="color:$danger;">*required</mark></td><td>Returns the information held by the account as a string.<br>Example) Roel 10: Car*ter This is<br>displayed directly to the user and serves as basic information provided to prevent confusion for users managing multiple accounts.</td></tr></tbody></table>

{% tabs %}
{% tab title="200" %}
```json
{
  "signature": [
    "rael 10: mag€€n",
    "server: arteria",
    "level: 85"
  ]
}
```
{% endtab %}
{% endtabs %}
