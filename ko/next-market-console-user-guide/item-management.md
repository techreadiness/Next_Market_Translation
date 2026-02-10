---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/item-management
---

# 아이템 관리

아이템 관리 페이지에서는 B2C 및 C2C 거래에 사용되는 아이템을 등록하고 관리할 수 있습니다.

해당 페이지를 통해 아이템 등록 API 기능을 Console 환경에서 제공합니다.

* 제공 기능
  * [미디어 파일 업로드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-media-upload)
  * [아이템 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item)
  * [아이템 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-sku)

## 아이템 등록 (개별 등록)

아이템 등록은 **개별 등록 방식**을 지원합니다.\
소량의 아이템을 등록하는 경우, 개별 등록을 통해 아이템을 생성할 수 있습니다.

{% stepper %}
{% step %}
### 아이템 관리 페이지 선택

* NEXT Market Console 접속
* 좌측 메뉴에서 **아이템 관리** 페이지 선택
{% endstep %}

{% step %}
### 아이템 등록 선택

* 아이템 등록 버튼을 선택하여 아이템 등록 화면으로 이동합니다.

<figure><img src="../.gitbook/assets/아이템 관리_아이템 등록.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 미디어 파일 업로드

* 아이템에 사용할 미디어 파일을 업로드합니다.

#### 업로드 방식

* URL 입력: 이미 업로드된 미디어 파일의 URL을 입력
* 파일 업로드: 로컬 파일 선택 후 업로드

#### 지원형식

* IMAGE: JPG, PNG, WebP

⚠️ VIDEO 형식 업로드는 기능상 선택은 가능하나, **공식적으로 지원하지 않으므로 IMAGE 형식으로만 등록해 주시기 바랍니다.**

#### 업로드 제한

* 파일 크기: 10MB 이하
* 이미지 사이즈: 배경 포함 72x72px

<figure><img src="../.gitbook/assets/아이템 관리_미디어 파일 업로드.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 기본 정보 입력

아이템의 기본 정보를 입력합니다.

| Field             | Value                                                                                                                                                                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SKU (Required)    | <ul><li>아이템을 식별하고 관리하기 위한 고유 품목 코드</li><li>중복 등록 불가</li><li><p>형식: 200자 미만의 사용자가 유추 가능한 값으로 영문, 숫자, 특수 문자 사용 가능</p><ul><li>특수 문자는 언더바 <code>_</code> 사용 불가하여 하이픈 <code>-</code>  사용을 권장</li></ul><p>⚠️ SKU는 실제 게임에서 사용하는 아이템 식별자와 동일한 값으로 입력 부탁드립니다.</p></li></ul> |
| 아이템 이름 (Required) | <ul><li>다국어 입력 지원: en, ko, ja, th, zh</li><li><p>아이템 목록 및 상세 화면에 표시되는 값</p><ul><li>마켓에서 제공하는 언어에 대해 반드시 등록 필요</li></ul></li></ul>                                                                                                                                  |
| 아이템 설명 (Required) | <ul><li>아이템 등록 페이지에서는 아이템 이름으로 설정</li><li>상세 설명이 필요한 경우, <strong>CSV 업로드 방식</strong>을 통해 별도 등록 필요</li></ul>                                                                                                                                                        |

<figure><img src="../.gitbook/assets/아이템 등록_기본정보.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 패키지 아이템 등록 (Optional)

* 패키지 아이템인 경우 선택하여 설정할 수 있습니다.

⚠️ 패키지 아이템에 포함되는 **서브 아이템은 반드시 사전에 등록되어 있어야 합니다.**

| Field     | Value                                    |
| --------- | ---------------------------------------- |
| 서브아이템 SKU | <ul><li>패키지 아이템의 구성 아이템 SKU 입력</li></ul> |
| 수량        | <ul><li>서브 아이템의 수량 입력</li></ul>          |

<figure><img src="../.gitbook/assets/아이템 등록_서브아이템.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### C2C 판매용 아이템 등록 (Optional)

* C2C 거래에 사용되는 아이템인 경우 선택하여 설정할 수 있습니다.

⚠️ C2C 판매용 아이템 등록 시 능력은 아이템(SKU) 단위로 입력하는 영역입니다. C2C 거래 시 아이템의 능력 표시 및 조건 검증에 활용될 수 있습니다.

| Field        | Value                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 능력 이름        | <ul><li>다국어 입력 지원: en, ko, ja, th, zh</li><li>능력 표시 이름</li><li>마켓에서 제공하는 언어에 대해 반드시 등록 필요</li></ul>                                                                                                                                                                                                                                                                                                                         |
| 옵션 타입        | <ul><li>능력 값이 어떤 성격의 정보인지를 정의함</li><li><p>옵션 타입 선택</p><ul><li>기본 능력치 (<code>BASIC</code>): 기본 능력치</li><li>제약 옵션 (<code>CONSTRAINT</code>): 변화에 의해 추가 또는 변경되는 제약 조건</li><li>아이템 포함 수량 (<code>AMOUNT</code>): 아이템에 내포된 수량을 표현하기 위한 값</li></ul></li><li>아이템 등록 API의 <code>abilties.optionType</code> 값으로 전달</li></ul><p>⚠️ <strong>아이템별로 변동되지 않는 기본 능력치는</strong> 아이템 관리 페이지에서 <strong>SKU 등록 시 함께 등록하는 것을 권장합니다.</strong></p> |
| 표시 형식        | <ul><li>능력 값을 <strong>어떤 형태로 사용자에게 보여줄지</strong> 설정</li><li><p>표시 형식 선택</p><ul><li>수치 그대로 (<code>NONE</code>): 입력 수치 그대로 노출</li><li>100% (<code>PPERCENTAGE</code>)</li><li>+100 (<code>NUMERIC</code>)</li><li>100Lv (<code>LEVEL</code>)</li></ul></li><li>아이템 등록 API의 <code>abilties.unitType</code> 값으로 전달</li></ul>                                                                                                    |
| 값            | <ul><li>Decimal 형식으로 입력</li><li>설정한 옵션 타입 및 표시 형식에 따라 화면에 표시</li><li>아이템 등록 API의 <code>abilties.value</code> 값으로 전달</li></ul>                                                                                                                                                                                                                                                                                               |
| 국가 접근 제한 설정  | <ul><li>C2C 아이템의 국가별 접근 제한 정책을 설정</li><li><p>제한 국가 접근 옵션 선택</p><ul><li>제한 없음</li><li>화이트리스트 (<code>policies.whitelist</code>)</li><li>블랙리스트 (<code>policies.blacklist</code>)</li><li>단, 화이트리스트와 블랙리스트는 <strong>동시에 적용 불가</strong></li></ul></li></ul>                                                                                                                                                                      |
| 최소 가격 (USDt) | <ul><li><p>C2C 아이템의 최소 판매가를 제한하는 정책</p><ul><li>설정된 최소 가격보다 낮은 가격으로 C2C판매 등록이 불가</li></ul></li><li><code>policies.minPrice</code></li></ul>                                                                                                                                                                                                                                                                                  |

<figure><img src="../.gitbook/assets/아이템 등록_C2C.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

## 아이템 등록 (벌크 등록)

아이템 벌크 등록은 **다수의 아이템을 한 번에 등록해야 하는 경우**, CSV 파일 업로드를 통해 아이템을 일괄 등록할 수 있는 기능입니다.

{% stepper %}
{% step %}
### 아이템 관리 페이지 선택

* NEXT Market Console 접속
* 좌측 메뉴에서 **아이템 관리** 페이지 선택
{% endstep %}

{% step %}
### 템플릿 다운로드

* **템플릿 다운로드** 버튼을 선택하여 아이템 벌크 등록용 **CSV 템플릿 파일**을 다운로드합니다.
* 템플릿에는 아이템 등록에 필요한 기본 컬럼이 포함되어 있습니다.

<figure><img src="../.gitbook/assets/아이템 관리_템플릿.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 아이템 리스트 작성하기

* 다운로드한 **CSV 템플릿 파일**에 등록할 아이템 정보를 입력합니다.
* 각 항목의 작성 방법은 **아이템 등록 (개별 등록)** 가이드를 참고하여 작성해 주세요.
* 단, imageUrl은 파일 업로드 대신 이미 업로드된 미디어 파일의 URL 입력 방식만 지원합니다.

⚠️ 필수 항목이 누락되거나 형식이 맞지 않을 경우 업로드가 실패할 수 있습니다.

<figure><img src="../.gitbook/assets/아이템 관리_csv 템플릿.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### CSV 업로드

* 작성이 완료된 CSV 파일을 선택하여 업로드합니다.
* 파일 선택 후 **업로드** 버튼을 클릭하면 아이템 벌크 등록이 진행됩니다.

#### ⚠️ 벌크 등록 시 유의사항

* CSV 업로드는 **신규 아이템 또는 기존 등록 아이템 정보 수정** 용도로 사용됩니다.
* CSV 업로드 등록 전, **소량 테스트 업로드**를 권장합니다.

<figure><img src="../.gitbook/assets/아이템 관리_csv 업로드.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

## 아이템 수정

아이템 수정은 **이미 등록된 아이템의 정보를 변경해야 하는 경우** 사용할 수 있는 기능입니다.\
NEXT Market Console에서는 아이템 수정을 위해 **개별 수정**과 **벌크 수정** 두 가지 방식을 제공합니다.

### 아이템 수정 방식

#### 개별 수정

개별 아이템의 정보를 수정하는 경우 사용합니다.

* **NEXT Market Console** 접속
* 좌측 메뉴에서 **아이템 관리** 페이지 선택
* 아이템 리스트에서 수정할 아이템 선택
* **수정하기** 버튼 클릭
* 아이템 정보 변경 후 저장

<figure><img src="../.gitbook/assets/아이템 관리_수정.png" alt=""><figcaption></figcaption></figure>

#### 벌크 수정

여러 아이템의 정보를 한 번에 수정해야 하는 경우 사용합니다.

* **아이템 관리** 페이지에서 **CSV 다운로드** 버튼 선택
* 다운로드한 CSV 파일에서 수정할 아이템 정보 변경
* 수정이 완료된 CSV 파일 업로드
* 업로드 완료 후 수정 결과 확인

<figure><img src="../.gitbook/assets/아이템 관리_csv 다운로드.png" alt=""><figcaption></figcaption></figure>

### ⚠️  수정 시 유의사항

* 판매 중인 아이템의 정보 변경은 서비스 운영에 영향을 줄 수 있습니다.
* 벌크 수정 전에는 **소량 테스트 수정**을 권장합니다.
