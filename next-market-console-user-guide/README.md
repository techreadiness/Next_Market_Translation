---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide
---

# NEXT Market Console 사용 가이드

## NEXT Market Console 소개

**NEXT Market Console**은 NEXT Market에서 제공하는 주요 API 기능을 **웹 기반 Console 형태로 제공**하여, 개발 및 운영 과정에서 **아이템·상품·미션을 쉽고 직관적으로 등록하고 관리할 수 있도록 지원하는 관리 도구**입니다.

## NEXT Market Console 이동하기

### Preview Environment

* URL: [https://app-console.nextmarket.games/](https://app-console.nextmarket.games/)
* 인증 정보: 개발사 회사 이메일 계정으로 신규 등록
  * Preview 환경 이용을 위해, 개발사 회사 이메일 계정으로 신규 계정을 등록해 주세요.
  * 계정 등록 완료 후 NEXT Market 담당자에게 연락하시면, 확인 절차를 거쳐 Console 이용 권한이 부여됩니다.

### Prod Environment

* URL: [https://console.nextmarket.games/](https://console.nextmarket.games/)
* 인증 정보: Biz Dashboard 권한이 부여된 이메일 계정 및 비밀번호
  * Console 이용을 위해서는 **Biz Dashboard 권한이 부여된 이메일 계정으로 로그인**해야 합니다.
  * **신규 유저의 경우**, 먼저 **계정 등록을 완료한 후 사업 담당자에게 연락**해 주시면, 확인 절차를 거쳐 **Console 이용 권한을 부여**해 드립니다.
  * 추가로 Biz Dashboard 권한 신청은 **사업 담당자를 통해 접수**하실 수 있으며, 권한 취득 후 **Biz Dashboard와 Console을 모두 이용**하실 수 있습니다.

## NEXT Market Console 제공 기능

NEXT Market Console에서는 NEXT Market API로 제공되는 주요 기능을 **웹 기반 Console** 환경에서 **직접 등록·관리**할 수 있습니다.

### [아이템 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/undefined)

B2C 및 C2C 거래에 사용되는 아이템을 등록하고 관리할 수 있습니다.

* 제공 기능
  * [미디어 파일 업로드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-media-upload)
  * [아이템 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item)
  * [아이템 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-sku)

### [B2C 상품 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/b2c)

B2C 상품의 판매 정보를 등록하고, 판매 상태를 관리할 수 있습니다.

* 제공 기능
  * [섹션 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#post-api-v1-sale-b2c-section)
  * [섹션 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#patch-api-v1-sale-b2c-section-sectionid)
  * [판매 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#post-api-v1-sale-b2c)
  * [판매 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#patch-api-v1-sale-b2c-b2csaleid)

### [C2C 아이템 능력 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/c2c)

C2C 아이템에 적용할 수 있는 **능력(속성)** 을 설정하고 관리할 수 있습니다.

* 제공 기능
  * [아이템 능력 설정 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item-ability)
  * [아이템 능력 설정 수정](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-ability-code)

### [미션 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/undefined-1)

미션을 생성하고 운영 상태를 관리할 수 있습니다.

* 제공 기능
  * [미션 생성](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#post-api-v1-incentive-mission)
  * [미션 수정](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#put-api-v1-incentive-mission-missionid)

## 안내 사항

⚠️ 아이템, 상품, 미션 등록 관련은 LINE NEXT와 사전 협의 후 진행해 주시기 바랍니다.

NEXT Market Console은 개발자뿐만 아니라 운영자도 직접 **아이템, 상품, 미션을 등록·관리**할 수 있는 웹 기반 관리 도구이며, Console에서 생성된 데이터는 **NEXT Market API와 동일한 방식으로 동작합니다.**

운영 관리상 수정이 필요한 경우, **각 변경 항목별 주의사항을 반드시 확인한 후 수정**해 주시기 바랍니다.\
또한, **이미 등록된 데이터에 대한 삭제 기능은 Console에서 제공하지 않으며, 삭제가 필요한 경우 API를 통해 진행해 주시기 바랍니다.**
