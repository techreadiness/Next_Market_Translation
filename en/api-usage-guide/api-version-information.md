metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/api-version-information
---

# Version Information

## Release Notes

### v1.10\_2025.09.10

* Provided sales volume statistics API

### v1.9\_2025.09.08

* Added referral code and custom payload when issuing one-time tokens
* Added custom payload parameter for shipping
* Added shipping history lookup API

### v1.8\_2025.08.22

* Changed mobile app WebView guide. Cookie → URL param(inapp=true)

### v1.7\_2025.07.24

* Added BadRequest if Region in [Store Authentication One-Time Token Request](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-1#undefined-2) is a Sanction Country

### v1.6\_2025.07.18

* Added [Mobile App WebView Guide](https://next-market-admin.gitbook.io/next-market-docs/api/undefined#v1.8_2025.08.22)

### v1.5\_2025.07.08

* Added [Sales Data Query](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C) Added items\[].skus, items\[].quantity
* [Sales Registration Request](https://github.com/tech-support-trade/docs/wiki/API-Guide#%ED%8C%90%EB%A7%A4-%EB%93%B1%EB%A1%9D-%EC%9A%94%EC%B2%AD) changed limitPurchaseCount to an optional field and updated its description.

### v1.4\_2025.07.04

* Supported multi-currency registration for B2C sales listings.
  * Removed price and currency input fields
  * Added multiCurrencyPrice input field
* Changed periodType field name → periodicType

### v1.3\_2025.07.01

* Added GREY and NONE values to color input field
* Changed link.deviceType from PC to WEB

### v1.2\_2025.06.26

* Modified color in item capability settings to content.color
* Added [C2C Sale Cancellation Request](https://github.com/tech-support-trade/docs/wiki/API-Guide#C2C-%ED%8C%90%EB%A7%A4-%EC%B7%A8%EC%86%8C-%EC%9A%94%EC%B2%AD)

### v1.1\_2025.06.24

* [Request for One-Time Token for Store Verification](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%9D%B8%EC%A6%9D%EC%9A%A9- Added parameter definition for issuing tokens for C2C sale registration
* Added c2cSaleId response field to [Sealing Request](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-20)
* Added labels for API availability environments (`preview` `prod`)
* Added [Sales Data Query](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C) (Available after 7/10)

### v1.0\_2025.05.27

* Defined API specs for B2C, C2C, Mission\&amp;Reward
* 🟡 Note: Some features are under review or only available in preview mode; verification is required before use.
