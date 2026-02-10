---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/api-usage-guide/api-list
---

# API 목록

## Game ➡️ Next Market

### 인증 및 보안&#x20;

* [서버 시간 체크](authentication-security.md#post-api-v1-server-time)
* [스토어 인증용 원타임 토큰 요청](authentication-security.md#post-api-v1-auth-token)
* [스토어 세션 킥](authentication-security.md#delete-api-v1-account-session-kick)

### B2C 아이템 등록

{% stepper %}
{% step %}
#### 아이템 요청

* [미디어 파일 업로드](item.md#post-api-v1-media-upload)
* [아이템 등록](item.md#post-api-v1-item)
* [아이템 변경](item.md#put-api-v1-item-sku)
* [아이템 조회](item.md#get-api-v1-item-sku)
* [아이템 목록 조회](item.md#get-api-v1-item)
{% endstep %}

{% step %}
#### 섹션 요청

* [섹션 등록 ](section.md#post-api-v1-sale-b2c-section)
* [섹션 변경](section.md#patch-api-v1-sale-b2c-section-sectionid)
* [섹션 목록 조회](section.md#get-api-v1-sale-b2c-section)
{% endstep %}

{% step %}
#### 판매 요청

* [판매 등록 ](sale.md#post-api-v1-sale-b2c)
* [판매 변경 ](sale.md#patch-api-v1-sale-b2c-b2csaleid)
* [판매 목록 조회](sale.md#get-api-v1-sale-b2c)
{% endstep %}
{% endstepper %}

### B2C 아이템 판매

* [원타임 토큰 요청](authentication-security.md#post-api-v1-auth-token)
* [판매량 통계 조회](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#get-api-v1-sale-b2c-statistics)
* [판매 등록](sale.md#post-api-v1-sale-b2c)
* [판매 변경](sale.md#patch-api-v1-sale-b2c-b2csaleid)
* [판매 목록 조회](sale.md#get-api-v1-sale-b2c)
* [B2C 판매 삭제](sale.md#delete-api-v1-sale-b2c-b2csaleid)

### C2C 아이템 등록

* [미디어 파일 업로드](item.md#post-api-v1-media-upload)
* [아이템 등록 ](item.md#post-api-v1-item)
* [아이템 능력 설정 등록 ](item.md#post-api-v1-item-ability)
* [아이템 능력 설정 수정](item.md#put-api-v1-item-ability-code)
* [아이템 능력 설정 목록 조회](item.md#get-api-v1-item-ability)

### C2C 아이템 판매&#x20;

* [원타임 토큰 요청](authentication-security.md#post-api-v1-auth-token)
* [아이템 배송 이력 조회](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#get-users-api-v1-item-send-item-guid-guid)
* [C2C 아이템 판매 취소](sale.md#delete-api-v1-sale-c2c-c2csaleid)

### 정산

* [매출 데이터 조회](settlement.md#get-api-v1-settlement)

### 미션

* [미션 생성](mission.md#post-api-v1-incentive-mission)
* [미션 수정](mission.md#put-api-v1-incentive-mission-missionid)
* [미션 제거](mission.md#delete-api-v1-incentive-mission-missionid)
* [업적 달성 기록 요청](mission.md#post-api-v1-incentive-mission-achieve)
* [미션 보드 조회](mission.md#get-api-v1-incentive-mission)



## Next Market ➡️ Game

### B2C 아이템 구매

* [계정 상태 조회](account.md#undefined)
* [아이템 배송](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined)
* [아이템 배송 결과 조회](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-2)

### C2C 아이템 구매

* [실링](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-4)
* [언실링 ](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-6)
* [계정 상태 조회](account.md#undefined)
* [아이템 교환](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-8)
* [아이템 교환 검증](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-10)

### 계정&#x20;

* [게임 계정 상태 조회](account.md#undefined)
