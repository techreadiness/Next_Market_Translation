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
* Added custom payload parameters during delivery
* Added delivery history lookup API

### v1.8\_2025.08.22

* Modified mobile app WebView guide. Cookie → URL param(inapp=true)

### v1.7\_2025.07.24

* Added BadRequest if [스토어 인증용 원타임 토큰 요청](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-1#undefined-2)&#x27;s Region is a Sanction Country

### v1.6\_2025.07.18

* Added [모바일 앱 WebView 가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined#v1.8_2025.08.22)

### v1.5\_2025.07.08

* Added [매출 데이터 조회](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C): items\[].skus, items\[].quantity
* Changed limitPurchaseCount to an optional field in [판매 등록 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#%ED%8C%90%EB%A7%A4-%EB%93%B1%EB%A1%9D-%EC%9A%94%EC%B2%AD) and updated its description.

### v1.4\_2025.07.04

* Supported multi-currency registration during B2C sales registration.
  * Removed price and currency input fields
  * Added multiCurrencyPrice input field
* Renamed periodType field → periodicType

### v1.3\_2025.07.01

* Added GREY and NONE values to color input field
* Changed link.deviceType from PC → WEB

### v1.2\_2025.06.26

* Changed color in item ability settings to content.color
* Added [C2C 판매 취소 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#C2C-%ED%8C%90%EB%A7%A4-%EC%B7%A8%EC%86%8C-%EC%9A%94%EC%B2%AD)

### v1.1\_2025.06.24

* Added parameter definition for token issuance for C2C sales registration to [스토어 인증용 원타임 토큰 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%9D%B8%EC%A6%9D%EC%9A%A9-%EC%9B%90%ED%83%80%EC%9E%84-%ED%86%A0%ED%81%B0-%EC%9A%94%EC%B2%AD)
* Added c2cSaleId response field to [실링 요청](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-20)
* Added labels for API availability environments (`preview` `prod`)
* Added [매출 데이터 조회](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C)(available after 7/10)

### v1.0\_2025.05.27

* Defined B2C, C2C, Mission\&amp;Reward; API spec
* 🟡 Note: Some features are under review or only available in preview, so verification is required before use.
