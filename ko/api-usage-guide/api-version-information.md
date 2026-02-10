---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/api-version-information
---

# 버전 정보

## 릴리즈 노트

### v1.10\_2025.09.10

* 판매량 통계 API 제공

### v1.9\_2025.09.08

* 원타임 토큰 발행시 레퍼럴코드와 커스텀 페이로드 추가
* 배송시 커스터 페이로드 파라미터 추가
* 배송 이력 조회 API 추가

### v1.8\_2025.08.22

* 모바일 앱 WebView 가이드 변경. Cookie → URL param(inapp=true)

### v1.7\_2025.07.24

* [스토어 인증용 원타임 토큰 요청](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-1#undefined-2)의 Region 기준에 Sanction Country일 경우 BadRequest 추가

### v1.6\_2025.07.18

* [모바일 앱 WebView 가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined#v1.8_2025.08.22) 추가

### v1.5\_2025.07.08

* [매출 데이터 조회](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C) items\[].skus, items\[].quantity 추가
* [판매 등록 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#%ED%8C%90%EB%A7%A4-%EB%93%B1%EB%A1%9D-%EC%9A%94%EC%B2%AD)에 limitPurchaseCount가 선택 필드로 변경되고 설명이 변경되었습니다.

### v1.4\_2025.07.04

* B2C 판매 등록 시 다중 통화 등록 지원.
  * price, currency 입력 값 삭제
  * multiCurrencyPrice 입력 값 추가
* periodType 필드 명칭 변경 → periodicType

### v1.3\_2025.07.01

* color 입력값에 GREY, NONE값 추가
* link.deviceType의 PC → WEB으로 변경

### v1.2\_2025.06.26

* 아이템 능력 설정에 color을 content.color로 수정
* [C2C 판매 취소 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#C2C-%ED%8C%90%EB%A7%A4-%EC%B7%A8%EC%86%8C-%EC%9A%94%EC%B2%AD) 추가

### v1.1\_2025.06.24

* [스토어 인증용 원타임 토큰 요청](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%9D%B8%EC%A6%9D%EC%9A%A9-%EC%9B%90%ED%83%80%EC%9E%84-%ED%86%A0%ED%81%B0-%EC%9A%94%EC%B2%AD)에 C2C 판매 등록용 토큰 발행을 위한 파라미터 추가 정의
* [실링 요청](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-20)에 c2cSaleId 응답 필드 추가
* API 이용 가능 환경에 대한 레이블 추가(`preview` `prod`)
* [매출 데이터 조회](https://github.com/tech-support-trade/docs/wiki/API-Guide#%EB%A7%A4%EC%B6%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%ED%9A%8C) 추가(7/10 이후 사용 가능)

### v1.0\_2025.05.27

* B2C, C2C, Mission\&Reward API spec 정의
* 🟡 주의: 일부 기능은 리뷰 중이거나 프리뷰에서만 사용할 수 있으므로 사용전 확인이 필요합니다.

