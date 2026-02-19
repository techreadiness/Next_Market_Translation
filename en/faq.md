metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/faq
---

# Frequently Asked Questions

## API Credentials

<details>

<summary>How can I obtain API Credentials?</summary>

After receiving corporate and store information and registering with NEXT Market, API Credentials will be issued. Once issued, they are delivered via email to the respective responsible personnel.

</details>## Firewall Exemption Procedure

<details>

<summary>Are there domain format restrictions?</summary>

For lowercase letters, numbers, and special characters, only hyphens (-) are permitted.

</details>

<details>

<summary>Why is firewall removal necessary?</summary>

NEXT Market and the game require bidirectional API calls, necessitating the removal of Inbound/Outbound firewall policies. ([Guide](/broken/pages/9MnL55l7VDyQw3jHyKjq))

</details>

<details>

<summary>How should dynamic IP addresses be communicated?</summary>

If using a dynamic IP, ACL registration is required each time, and processing may take approximately 3 business days. Therefore, we recommend using a static IP.

</details>

<details>

<summary>How do I verify normal operation after disabling the firewall?</summary>

```
curl --user &quot;{apiKey}:{credential}&quot; \
 -X POST https://app-sdk.nextmarket.games/api/v1/server/time \
 -H &quot;Content-Type: application/json&quot;
```

</details>

<details>

<summary>Can I use a custom port number on the developer&#x27;s server domain?</summary>

Yes, it is possible.
However, in the Preview environment, if you use **ports 80 or 443**, **NEXT Market → Game Outbound ACL configuration is unnecessary**.
Therefore, if you want to test quickly, we recommend using port 80 or 443.

</details>

<details>

<summary>When calling the Server Time Check API (<a href="https://sdk.nextmarket.games/api/v1/server/time"><code>https://sdk.nextmarket.games/api/v1/server/time</code></a>), a webpage is returned instead of JSON. Why is this happening?</summary>

This is because access is denied due to incomplete ACL configuration.

</details>## API

<details>

<summary>What format does the API use for Timestamp?</summary>

It uses a 13-digit integer value in milliseconds.

</details>

<details>

<summary>What are the response headers/format for the Game Account Verification API?</summary>

The response must be in the `Content-Type: application/json` format.

</details>

<details>

<summary>What is the error response format when calling the API?</summary>

Error responses have the following JSON structure:

```
{
  &quot;code&quot;: &quot;error code&quot;,
  &quot;message&quot;: &quot;error message&quot;
}
```

</details>

<details>

<summary>Can I add an authentication header to the NEXT Market -&gt; Game callback?</summary>

Yes, it is possible. Custom implementations such as API Key/Secret or token-based methods can be applied.

</details>

<details>

<summary>Do Preview and Prod environments need to be configured independently?</summary>

Yes, they must be configured independently.

</details>## One-time authentication token for store authentication

<details>

<summary>What is a one-time authentication token for store authentication?</summary>

It is a token that allows a user authenticated in the game to log in as a store-authenticated user.

Navigating to https://{domain}.nextmarket.games/auth?token={token} in an external browser will grant access as an authenticated user.

</details>

<details>

<summary>How do I request a one-time authentication token for store authentication?</summary>

One-time token issuance is handled via server-to-server communication. The game client must receive and process the response result.

</details>

<details>

<summary>What is redirectPath?</summary>

This parameter is used to redirect to a specific page after authentication. If not set, the default redirect is to the B2C sales page.

</details>

<details>

<summary>How do I configure the redirectPath?</summary>

How to set redirectPath

* B2C page: /shop
* C2C page: /marketplace
* Mission &amp; Rewards page: /mission

However, for C2C sales registration, the set redirectPath is ignored, and the user is directed directly to the C2C sales registration page.

Additionally, except for C2C sales registration, query parameters can be specified. This allows navigation to a specific product location or the inclusion of UTM code parameters.

</details>

<details>

<summary>What are examples of store navigation links?</summary>

Example link: https://{domain}/auth?token=xxxx\&amp;redirectPath;=/xxxx/xxx?param=key 

</details>

<details>

<summary>What is the validity period of the one-time authentication token for store authentication?</summary>

The token expires immediately after use, while the session persists separately.

The session renews hourly based on user activity and can be extended up to 180 days, though this may vary operationally. 

</details>

<details>

<summary>Why is an error returned when region is set to ALL?</summary>

The error occurs because NEXT Market cannot recognize the region.

The region must be provided as an agreed-upon country code([https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2), uppercase format).

</details>

<details>

<summary>Can the signature value be replaced with something other than the server/character?</summary>

You can set any value as long as it is a string that can be publicly disclosed to the logged-in user.

</details>## Game Account Status Inquiry

<details>

<summary>Is {{endpoint}}/next-market/ fixed?</summary>

The path following the endpoint is fixed.

However, if setting the root path to `/next-market` is difficult, you can configure a subpath using the format `https://{domain}/{subpath}/next-market/…`. Share this subpath (including `subpath`) with the development team for configuration.

</details>## Items

<details>

<summary>Is there an SKU format?</summary>

We recommend setting values under 200 characters that users can easily infer.

When using special characters, the underscore `_` separator cannot be used; hyphen `-` is recommended.

</details>

<details>

<summary>What are the mandatory values when registering items for B2C sales?</summary>

name, description, subItemList (optional), policies.whiteList (optional), and policies.blacklist (optional) must be registered.



</details>

<details>

<summary>Is SKU registration required for both B2C and C2C?</summary>

Yes, that&#x27;s correct. SKU registration is mandatory for items requiring shipping and transaction processing. (Register via API)

</details>

<details>

<summary>Do package sub-items also need to be registered?</summary>

Yes, that&#x27;s correct. All sub-items must be registered individually for package screen display and transmission processing.

</details>

<details>

<summary>Does subItemList reference the individually registered SKUs?</summary>

It is used solely for referencing and displaying the registered individual SKUs.

</details>

<details>

<summary>How do I add line breaks in the item description?</summary>

You can apply line breaks using the `\n` or `<br>

` tags.

</details>

<details>

<summary>How should language codes be displayed?</summary>

For `lang`, you must use lowercase letters and underscores (`_`). It must be managed separately from the `region` in the one-time authentication token.

However, since ISO-639-1 does not simultaneously support Simplified and Traditional Chinese, we only support Traditional Chinese and not Simplified Chinese. If Simplified Chinese support is required, separate exception handling is necessary to maintain backward compatibility, so consultation is needed.

</details>

<details>

<summary>What are the specifications for registering item images?</summary>

Items must use a 72x72px size, including the background.

</details>

<details>

<summary>Can LINE NEXT handle API calls like item registration on our behalf?</summary>

This requires discussion. If you need assistance, LINE NEXT can handle the registration if you provide the parameter values in TSV or JSON format.

</details>## Sales

<details>

<summary>How do I use the sku, serialNumber, and amount parameters when registering C2C items?</summary>

Example)

* Single item: `sku=abc1, amount=1`
* Stackable item: `sku=abc2, amount=20`
* Variant item: `sku=abc3, serialNumber=xxxx, amount=1`

</details>

<details>

<summary>How do I register a package product?</summary>

Register the package SKU and map the sub-items to `subItemList.sku`.

</details>

<details>

<summary>What are the specifications for product image registration?</summary>

Products must use a 514x514px size including the background.

</details>

<details>

<summary>Can I modify the price or currency after listing a product?</summary>

No. If changes to price or composition are needed, a new sales registration must be created.

</details>

<details>

<summary>How do limitPurchaseCount, periodicType, and resetAt work?</summary>

* limitPurchaseCount: 1 &amp; periodicType: null &amp; resetAt: null:  First purchase allowed per account
* limitPurchaseCount: 1 &amp; periodicType: is not null &amp; resetAt: is not null:  One purchase allowed per period, with purchase count reset at period start
* limitPurchaseCount: null: No purchase limit

</details>

<details>

<summary>Can I delete a listed item?</summary>

Items that have started selling or have a sales history cannot be deleted. However, items that have not yet started selling can be deleted.

</details>

<details>

<summary>How do I check the saleId after requesting a sale registration?</summary>

The ID returned after registration is the saleId.

</details>

<details>

<summary>For package products, which value is used for quantity display / delivery quantity?</summary>

It is displayed based on the subItemList.amount value.

</details>

<details>

<summary>What is section registration?</summary>

A list of sections is required to display B2C products. If only one section exists, a single column is used. If two or more sections exist, the top tabs and anchors on the webshop will function.

</details>## Payment

<details>

<summary>What currencies are supported?</summary>

For fiat payments, we support USD, JPY, THB, PHP, IDR, TWD, and KRW. For crypto payments, we support USDt.

For unsupported currencies, payment can be made in USD.

</details>

<details>

<summary>How do I test actual payments?</summary>

Virtual payments are processed in the Preview environment, while the Prod environment requires actual credit card payments (testing is only possible with international credit cards).

</details>

<details>

<summary>How does multiCurrencyPrice work?</summary>

The locally set currency for each country takes precedence. If that currency is unavailable, prices are displayed in USD.

</details>

<details>

<summary>What happens if multiCurrencyPrice is set to 0?</summary>

It is processed as a free purchase.

</details>

<details>

<summary>What are the minimum payment amounts per currency?</summary>

Minimum payment amount per currency

* USD: 0.01
* JPY: 1
* THB: 1
* PHP: 6
* IDR: 1,000
* TWD: 30
* KRW: 10

The minimum price for B2C products must be set above the minimum payment amount per currency. Therefore, consultation with LINE NEXT is required before finalizing prices.

</details>## Shipping

<details>

<summary>What is the format for the requestId when making a delivery request?</summary>

It does not need to be in UUID format and may include a specific prefix. However, it must be unique for every request.

</details>

<details>

<summary>How are duplicate requests handled?</summary>

Uniqueness is guaranteed. Even if the same request occurs multiple times, the requestId will be identical. You can recognize it as a duplicate request and reject it.

</details>

<details>

<summary>Can purchase history be checked using the requestId?</summary>

It is used solely as an identifier for delivery requests. While it can be used to verify the result of requests between servers, it cannot be utilized as an identifier for separate inquiries such as purchase history.

</details>

<details>

<summary>Can shipping requests be delayed after a successful payment?</summary>

Delays may occur due to simultaneous purchase volumes, but a reprocessing mechanism exists to prevent issues.

</details>

<details>

<summary>Regarding delivery history lookup, if a delivery isn&#x27;t received, does acquiredAt show as 0?</summary>

acquiredAt signifies the delivery completion time, so it always has a value. If a delivery failure occurs, the query result will show no value. In such cases, it must be judged as an abnormal delivery.

</details>## Refunds

<details>

<summary>How are refunds processed?</summary>

Refunds follow this sequence: User request → Developer retrieves the item → Decision to process the refund after settlement review → Refund via the PG company. All refunds are processed manually.

</details>

<details>

<summary>How are refund notices applied?</summary>

Guidance text can only be adjusted by country in the web shop. In-game, the &quot;no refunds&quot; policy text is used for consistency.

</details>

<details>

<summary>Are refunds possible for payment tests in the Prod environment?</summary>

Yes, they are possible. However, since PG company fees are incurred for payments/cancellations in the Prod environment, both the developer and NEXT bear the cancellation fees.

* Notes and Cancellation Fees
  * Testing is only possible with international credit card payments
  * $0.3 + VAT incurred per payment/cancellation
    * $0.66 incurred when canceling after payment
  * Contractual fees will be deducted from the next month&#x27;s settlement → Shared by the developer and NEXT

</details>## Settlement

<details>

<summary>How is settlement processed?</summary>

Sales settlement targets are aggregated monthly. Here is the timeline:

* Sales aggregation and verification: 3 business days into the following month
* Biz Report provision: 4th ~ 5th business day into the following month
* Settlement instruction: 20th of the following month
* Settlement payment: 21st of the following month

</details>## Missions &amp; Rewards

<details>

<summary>What if a mission cannot be verified after registration?</summary>

After the developer registers a mission, NEXT Market must additionally set the reward and release time. The mission will be displayed at the scheduled release time once these settings are complete.

</details>

<details>

<summary>Can mission completion be checked per character?</summary>

Depending on the game, mission completion status is managed either per game account or per character.

However, if character-level verification is required, a separate character-level GUID must be generated. This requires configuration discussions with NEXT Market.

</details>

<details>

<summary>How does the flow for mission completion verification and user reward receipt proceed?</summary>

[View Flow](https://github.com/tech-support-trade/docs/wiki/%EB%AF%B8%EC%85%98-%EB%8B%AC%EC%84%B1-%ED%99%95%EC%9D%B8%EA%B3%BC-%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%B3%B4%EC%83%81-%EC%88%98%EB%A0%B9)

</details>

<details>

<summary>Why is the mission participation button hidden in mobile/tablet environments?</summary>

The default participation button on the mission page links to an external page. In webview environments, it is hidden to prevent users from leaving the app. Once the mission is completed or subsequent steps are finished, the reward button or reward payment completion button will display normally.

It is displayed on PC environments and is only hidden as described above in mobile/tablet environments.

</details>

<details>

<summary>What are the mission types?</summary>

* SINGLE: Ends upon achieving the set goal and resets afterward.
* ACCUMULATE: Accumulates values continuously.
  * Example: After completing 20/20, reaching 40 is processed as 40/40.
* DIFFICULTY: Increases the target value and difficulty per round. Starts from 0 again after completion.
  * Example: Round 1: Kill 20 enemies (0/20) → Round 2: Kill 40 enemies (0/40)
* CHALLENGE: Set ongoing missions as a collection. All designated missions must be completed together to receive rewards.

</details>## Web Shop

<details>

<summary>What determines which languages are displayed in the Webshop?</summary>

The priority order is as follows:

* Select the languages to support in the web shop from the 5 languages provided by NEXT Market, and set the store&#x27;s default language from among them.
  * Available languages: English, Korean, Japanese, Chinese (Traditional), Thai
* Non-logged-in users: Store default language
* Logged-in users: User&#x27;s set language or language set in the footer
  * However, if the user&#x27;s browser/OS language is not one provided by NEXT Market, the store default language is displayed

</details>

<details>

<summary>If I open the Preview environment using a token issued in the Prod environment, will the Prod web shop appear?</summary>

Preview and Prod are completely independent environments, so authentication will not work. The Prod web shop has a separate domain.

</details>## Webview

<details>

<summary> How can NEXT Market be provided as an in-game Webview?</summary>

If you plan to provide NEXT Market via an in-game Webview, prior notification to LINE NEXT is required.

For details, please refer to the following guide document: ([가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-8#market-webview))

</details>## Testing

<details>

<summary>Are there any precautions during Preview testing?</summary>

The Preview Store is a page that may be visible to general users. Therefore, care must be taken to ensure that actual products, items, prices, or other information that should not be disclosed to general users in advance is not entered.

</details>

<details>

<summary>What should be verified during Preview testing?</summary>

We recommend focusing on:
- Navigation flow when moving from the game to the web shop (via Webview or external browser)
- Login functionality
- Item delivery after purchasing products

To address any issues discovered during testing, please complete testing for the above items at least 3 business days before the web shop launch.

</details>

<details>

<summary>Why is inspection mode enabled in the Preview environment?</summary>

We conduct testing with inspection mode enabled in the Preview environment to enhance accessibility and prevent general users from accessing the store before its official release. Please note that testing will follow the same procedure with inspection mode enabled at the Prod launch as well.

For detailed information, please refer to the following guide document: ([가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-8#market))

</details>

<details>

<summary>How should I test products registered only in TWD with other currencies like USD or JPY?</summary>

You must register the product again and then proceed with testing. However, please note that in unavoidable cases, testing support may be possible after consultation with LINE NEXT.

</details>## Policy

<details>

<summary>Can I use NEXT Market if my game account is restricted?</summary>

No. NEXT Market is only accessible after logging into the game, so it cannot be used if the game account is restricted. However, viewing the item list may still be possible.

</details>
