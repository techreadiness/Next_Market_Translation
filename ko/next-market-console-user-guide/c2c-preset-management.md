---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/c2c-preset-management
---

# C2C 프리셋 관리

**C2C 프리셋 관리 페이지는 C2C 아이템에 사용되는 카테고리 (아이템 분류 계층 구조)를 등록·관리하는 페이지입니다.**\
C2C 아이템의 카테고리 정보를 사전에 등록한 뒤, C2C 판매 등록 시 해당 카테고리를 선택하여 사용할 수 있습니다. \
카테고리 설정 시 Marketplace의 필터 영역에 반영되며, 카테고리별로 아이템이 노출됩니다.

<figure><img src="../../.gitbook/assets/프리셋.png" alt=""><figcaption></figcaption></figure>

## C2C 프리셋 등록

C2C 아이템 카테고리 설정은 최대 2 Depth까지 설정 가능합니다.

* 레벨 1: 부모 프리셋
* 레벨 2: 하위 프리셋

{% stepper %}
{% step %}
### C2C 프리셋 관리 페이지 선택

* NEXT Market Console 접속
* 좌측 메뉴에서 **C2C 프리셋 관리** 페이지 선택
{% endstep %}

{% step %}
### 프리셋 생성 선택

* 프리셋 생성 버튼을 선택하여 등록 화면으로 이동합니다.

<figure><img src="../../.gitbook/assets/프리셋_등록.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 기본 정보 입력

프리셋 (카테고리)의 기본 정보를 입력합니다.

| Field      | Value                                                                                                                                                                                                                                 |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 레벨         | <ul><li><p>프리셋은 레벨 1 ~ 2까지 설정 가능</p><ul><li>레벨 1은 최상위 카테고리로, 부모 프리셋을 설정할 수 없음</li><li>레벨 2는 레벨 1 하위 카테고리로 등록됨</li></ul></li><li><p>Ex)</p><ul><li>레벨 1: 무기</li><li>레벨 2: 활, 대검, 지팡이, 석궁, 단검</li></ul></li></ul>                       |
| 부모 프리셋     | <ul><li><p>레벨 2 프리셋 등록 시, 부모 프리셋 (레벨 1)을 설정 필요</p><ul><li>레벨 1 프리셋은 부모 프리셋 설정을 할 수 없음</li></ul></li><li><p>Ex)</p><ul><li>프리셋: 활</li><li>부모 프리셋: 무기</li></ul></li></ul>                                                               |
| 색상         | <ul><li>카테고리에 표시될 색상을 설정</li><li>설정 가능 색상: 파란색, 노란색, 빨간색, 초록색</li><li>없음 선택 시 기본색상이 적용</li></ul><p>⚠️ 색상 설정은 등급 (희귀도) 카테고리에만 등록하는 것을 권장합니다.</p><ul><li><p>Ex) </p><ul><li>전설: 노란색</li><li>희귀: 파란색</li><li>고급: 초록색</li></ul></li></ul> |
| 프리셋명 (다국어) | <ul><li>다국어 입력 지원: en, ko, ja, th, zh</li><li><p>거래소 내 아이템 상세 화면에 표시되는 값</p><ul><li>마켓에서 제공하는 언어에 대해 반드시 등록 필요</li></ul></li></ul>                                                                                                    |

<figure><img src="../../.gitbook/assets/프리셋_기본정보.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 아이템 등록

프리셋에 포함될 아이템 (SKU) 설정은 프리셋 최초 등록 시가 아닌, 등록 완료 후 수정 기능을 통해 등록 가능합니다.

<figure><img src="../../.gitbook/assets/프리셋_아이템.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

## C2C 프리셋 수정

**이미 등록된 프리셋의 정보는 수정할 수 있습니다.**

* **NEXT Market Console** 접속
* 좌측 메뉴에서 **C2C 프리셋 관리** 페이지 선택
* 프리셋 리스트에서 수정할 프리셋 선택
* **수정하기** 버튼 클릭
* 프리셋 정보 변경 후 저장

<figure><img src="../../.gitbook/assets/프리셋_수정.png" alt=""><figcaption></figcaption></figure>

### ⚠️  수정 시 유의사항

* 프리셋 등록은 LINE NEXT와 사전 협의 후 진행해 주시기 바랍니다.
* 프리셋의 레벨 수정은 불가능합니다. 레벨 변경이 필요한 경우 새로운 프리셋을 등록해야 합니다.
* 이미 운영 중인 프리셋의 정보 변경은 서비스 운영에 영향을 줄 수 있습니다.
