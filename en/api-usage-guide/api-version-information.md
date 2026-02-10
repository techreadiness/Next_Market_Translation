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

* Added `items[].skus` and `items[].quantity` to [Sales Data Query](https://github.com/tech-support-trade/docs/wiki/API-Guide#매출-데이터-조회)
* [Sales Registration Request](https://github.com/tech-support-trade/docs/wiki/API-Guide#판매-등록-요청): limitPurchaseCount changed to an optional field and description updated.

### v1.4\_2025.07.04

* Supported multi-currency registration for B2C sales.
  * Removed price and currency input fields
  * Added multiCurrencyPrice input field
* Changed periodType field name → periodicType

### v1.3\_2025.07.01

* Added GREY and NONE values to color input field
* Changed link.deviceType from PC → WEB

### v1.2\_2025.06.26

* Item ability settings: Changed color to content.color
* Added [C2C Sale Cancellation Request](https://github.com/tech-support-trade/docs/wiki/API-Guide#C2C-판매-취소-요청)

### v1.1\_2025.06.24

* Added parameter definition for issuing tokens for C2C sale registration to [Store Authentication One-Time Token Request](https://github.com/tech-support-trade/docs/wiki/API-Guide#스토어-인증용-원타임-토큰-요청)
* Added c2cSaleId response field to [Sealing Request](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-20)
* Added labels for API availability environment (`preview` `prod`)
* Added [Sales Data Query](https://github.com/tech-support-trade/docs/wiki/API-Guide#매출-데이터-조회) (Available after 7/10)

### v1.0\_2025.05.27

* B2C, C2C, Mission\
