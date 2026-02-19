metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide
---

# NEXT Market Console User Guide

## Introduction to NEXT Market Console

**NEXT Market Console** is a management tool that provides the main API functions offered by NEXT Market in a **web-based console format**. It supports the **easy and intuitive registration and management of items, products, and missions during development and operation processes**.

## Accessing the NEXT Market Console

### Preview Environment

* URL: [https://app-console.nextmarket.games/](https://app-console.nextmarket.games/)
* Credentials: Register a new account using your company&#x27;s development email address
  * To use the Preview environment, please register a new account using your company&#x27;s development email address.
  * After completing account registration, contact your NEXT Market representative. Following verification, Console access permissions will be granted.

### Prod Environment

* URL: [https://console.nextmarket.games/](https://console.nextmarket.games/)
* Credentials: Email account and password with Biz Dashboard permissions
  * To use the Console, you must **log in with an email account that has Biz Dashboard permissions**.
  * **For new users**, please first **complete account registration and then contact your business representative**. After verification, **Console access will be granted**.
  * Additionally, Biz Dashboard permission requests can be **submitted through your business representative**. After obtaining permissions, you can **use both Biz Dashboard and the Console**.

## NEXT Market Console Features

The NEXT Market Console allows you to **directly register and manage** key features provided by the NEXT Market API within a **web-based Console** environment.

### [아이템 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/undefined)
Register and manage items used in B2C and C2C transactions.

* Features Provided
  * [미디어 파일 업로드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-media-upload)
* [아이템 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item)
* [아이템 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-sku)
### [B2C 상품 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/b2c)
Register sales information for B2C products and manage their sales status.

* Features Provided
  * [섹션 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#post-api-v1-sale-b2c-section)
* [섹션 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#patch-api-v1-sale-b2c-section-sectionid)
* [판매 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#post-api-v1-sale-b2c)
* [판매 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#patch-api-v1-sale-b2c-b2csaleid)
### [C2C 아이템 능력 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/c2c)
Set and manage **attributes** applicable to C2C items.

* Features Provided
  * [아이템 능력 설정 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item-ability)
* [아이템 능력 설정 수정](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-ability-code)
### [미션 관리](https://next-market-admin.gitbook.io/next-market-docs/~/revisions/qUnx3GRV3SuUkB0oDqWL/next-market-console/undefined-1)
Create missions and manage their operational status.

* Features Provided
  * [미션 생성](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#post-api-v1-incentive-mission)
* [미션 수정](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#put-api-v1-incentive-mission-missionid)
## Important Notice

⚠️ Please consult with LINE NEXT beforehand regarding the registration of items, products, and missions.

The NEXT Market Console is a web-based management tool that allows not only developers but also operators to directly **register and manage items, products, and missions**. Data created within the Console **operates identically to the NEXT Market API.**

If modifications are necessary for operational management, **please ensure you review the specific precautions for each change item before making any alterations.**
Additionally, **the Console does not provide a delete function for already registered data. If deletion is required, please proceed via the API.**
