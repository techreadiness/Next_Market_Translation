---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/faq
---

# 자주 묻는 질문

## API Credentials

<details>

<summary>API Credentials 정보는 어떻게 받을 수 있나요?</summary>

법인, 스토어 정보 수령 후 NEXT Market에 등록되면 API Credentials 정보가 발급됩니다. 발급 이후에는 각 담당자 메일을 통해 전달드리고 있습니다.

</details>

## 방화벽 해제 절차

<details>

<summary>도메인 형식이 있나요?</summary>

소문자, 숫자, 특수 문자의 경우에는 하이픈(-)만 허용하고 있습니다.

</details>

<details>

<summary>방화벽 해제는 왜 해야 하나요?</summary>

NEXT Market과 게임은 양방향 API 호출이 필요하여, Inbound/Outbound 방화벽 정책 해제 처리가 필요합니다. ([Guide](/broken/pages/9MnL55l7VDyQw3jHyKjq))

</details>

<details>

<summary>유동 IP 처리는 어떻게 전달해야 하나요?</summary>

유동 IP를 사용할 경우 매번 ACL 등록이 필요하며, 처리에 약 3영업일이 소요될 수 있습니다. 하여 고정 IP 사용을 권장합니다.

</details>

<details>

<summary>방화벽 해제 후 정상 동작을 어떻게 검증하나요?</summary>

```
curl --user "{apiKey}:{credential}" \
 -X POST https://app-sdk.nextmarket.games/api/v1/server/time \
 -H "Content-Type: application/json"
```

</details>

<details>

<summary>개발사 서버 도메인에서 Custom 포트 넘버를 사용해도 되나요?</summary>

네, 가능합니다.\
단, Preview 환경에서는 **80, 443 포트**를 사용하는 경우 **NEXT Market → Game Outbound ACL 설정이 불필요**합니다.\
따라서 빠른 테스트를 원하신다면 80 또는 443 포트 사용을 권장드립니다.

</details>

<details>

<summary>서버시간 체크 API (<a href="https://sdk.nextmarket.games/api/v1/server/time"><code>https://sdk.nextmarket.games/api/v1/server/time</code></a>) 호출 시 JSON 대신 웹페이지가 반환됩니다. 이유가 무엇인가요?</summary>

ACL 설정이 완료되지 않아 접근이 거부된 상태이기 때문입니다.

</details>

## API

<details>

<summary>API에서 Timestamp 형식은 무엇을 사용하나요?</summary>

밀리초 단위의 13자리 정수 값을 사용합니다.

</details>

<details>

<summary>게임 계정 확인 API 응답 헤더/포맷은 어떻게 되나요?</summary>

`Content-Type: application/json` 형식으로 응답해야 합니다.

</details>

<details>

<summary>API 호출 시 에러 응답 포맷은 어떻게 되나요?</summary>

에러 응답은 다음과 같은 JSON 구조를 가집니다.

```
{
  "code": "에러코드",
  "message": "에러메시지"
}
```

</details>

<details>

<summary>NEXT Market -> Game 콜백에도 인증 헤더를 추가할 수 있나요?</summary>

가능합니다. API Key/Secret, 토큰 방식 등 맞춤 적용이 가능합니다.

</details>

<details>

<summary>Preview와 Prod 환경은 독립적으로 구성해야 하나요?</summary>

네 맞습니다. 독립적으로 구성되어야 합니다.

</details>

## 스토어 인증용 원타임 인증 토큰

<details>

<summary>스토어 인증용 원타임 인증 토큰이 뭔가요?</summary>

게임에서 인증된 사용자가 스토어로 인증된 사용자로 로그인하기 위한 토큰입니다.

https://{domain}.nextmarket.games/auth?token={token} 로 external browser로 이동하면 인증된 사용자로 진입하게 됩니다.

</details>

<details>

<summary>스토어 인증용 원타임 인증 토큰은 어떻게 요청하나요?</summary>

원타임 토큰 발급은 서버 간 통신(server-to-server)으로 처리하며, 응답 결과를 게임 클라이언트에서 받아 처리해야 합니다.

</details>

<details>

<summary>redirectPath는 무엇인가요?</summary>

인증 후 특정 페이지로 바로 이동하고자 할 때 사용하는 파라미터입니다. 설정하지 않으면 기본적으로 B2C 판매 페이지로 이동합니다.

</details>

<details>

<summary>redirectPath 설정은 어떻게 하나요?</summary>

redirectPath 설정 방법

* B2C 페이지: /shop
* C2C 페이지: /marketplace
* 미션&리워드 페이지: /mission

단, C2C 판매 등록의 경우 설정된 redirectPath를 무시하고 바로 C2C 판매등록 페이지로 이동됩니다.

추가로 C2C 판매 등록의 경우를 제외한 나머지 경우는 query parameter를 지정할 수 있으니 특정 상품의 위치로 이동하거나 utm 코드 파라미터를 지정하는 것도 가능합니다.

</details>

<details>

<summary>스토어 이동 링크 예시는 어떻게 되나요?</summary>

링크 예시: https://{domain}/auth?token=xxxx\&redirectPath=/xxxx/xxx?param=key&#x20;

</details>

<details>

<summary>스토어 인증용 원타임 인증 토큰의 유효기간은 어떻게 되나요?</summary>

토큰은 1외 사용 시 바로 소멸하며, 세션은 별도로 유지됩니다.

세션의 경우 유저의 활동 시 1시간 단위로 갱신되며, 최대 180일까지 연장 가능하지만 운영상 변동 가능성은 있습니다.&#x20;

</details>

<details>

<summary>region에 ALL로 설정했는데 에러가 반환되는 사유가 뭔가요?</summary>

NEXT Market에서 region을 인식하지 못하기 때문에 에러가 발생합니다.&#x20;

region은 협의된 국가코드 ([https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2), 대문자 형식)로 전달주셔야 합니다.

</details>

<details>

<summary>signature 값은 서버 / 캐릭터가 아닌 다른 값으로 대체해도 되나요?</summary>

로그인 유저에게 공개 가능한 문자열이면 어떤 값이든 설정해주시면 됩니다.

</details>

## 게임 계정 상태 조회

<details>

<summary>{{endpoint}}/next-market/은 고정인가요?</summary>

endpoint 뒤에 경로는 고정입니다.&#x20;

단, root path에 /next-market으로 지정이 어려운 경우에는 https://{domain}/{subpath}/next-market/… 형식으로 하위 경로를 구성한 뒤에 subpath 포함하여 개발팀 공유하면 설정 가능합니다.

</details>

## 아이템

<details>

<summary>SKU 형식이 있나요?</summary>

200자 미만의 사용자가 유추 가능한 값으로 설정하는 것을 권장하고 있습니다.

특수 문자 사용 시 언더바 `_` 구분자는 사용이 불가하며, 하이픈 `-` 사용을 권장합니다.

</details>

<details>

<summary>B2C 판매 예정인 아이템 등록 시 필수로 입력해야 하는 값이 뭔가요?</summary>

name, description, subItemList(optional), policies.whiteList(optional), polices.blacklist(optional)은 필수로 등록해주셔야 합니다.



</details>

<details>

<summary>B2C와 C2C에서 모두 SKU 등록이 필요한가요?</summary>

네 맞습니다. 배송 및 거래를 위한 아이템은 반드시 SKU 등록이 필요합니다. (API를 통해 등록)

</details>

<details>

<summary>패키지 하위 아이템도 등록이 필요한가요?</summary>

네 맞습니다. 패키지 화면 노출 및 전송 처리를 위해 모든 하위 아이템도 개별적으로 등록해야 합니다.

</details>

<details>

<summary>subItemList는 등록한 개별 SKU를 참조하나요?</summary>

등록한 개별 SKU를 참조하여 표시하는 용도로만 사용하고 있습니다.

</details>

<details>

<summary>아이템 설명에서 줄바꿈은 어떻게 하나요?</summary>

`\n` 또는 `<br>` 태그를 사용하여 줄바꿈을 적용할 수 있습니다.

</details>

<details>

<summary>언어코드 표기는 어떻게 하나요?</summary>

lang의 경우 반드시 소문자와 언더바(\_)를 사용해야 하며, 원타임 인증 토큰의 region과는 별도로 운영하셔야 합니다.

단, ISO-639-1에서 간체, 번체를 동시에 지원하지 않기 때문에 간체는 지원하지 않고 번체만 지원하고 있습니다. 만약 간체 적용이 필요하신 경우에는 하위호환성 유지를 위해 별도의 예외처리가 필요하여 협의가 필요합니다.

</details>

<details>

<summary>아이템 이미지 등록 규격은 어떻게 되나요?</summary>

아이템은 배경 포함 72x72px 사이즈를 사용해야 합니다.

</details>

<details>

<summary>아이템 등록 등의 API 호출을 LINE NEXT에서 대신 처리해줄 수 있나요?</summary>

협의가 필요한 부분으로, 대행이 필요하다면 TSV 또는 JSON 형식으로 파라미터 값을 전달하면 LINE NEXT에서 등록을 대행할 수 있습니다.

</details>

## 판매

<details>

<summary>C2C 등록 시 sku, serialNumber, amount 파라미터는 어떻게 사용하나요?</summary>

예시)

* 단일 아이템: `sku=abc1, amount=1`
* 스택형 아이템: `sku=abc2, amount=20`
* 변형 아이템: `sku=abc3, serialNumber=xxxx, amount=1`

</details>

<details>

<summary>패키지 상품 등록은 어떻게 하나요?</summary>

패키지 SKU를 등록하고, 하위 아이템은 `subItemList.sku`에 매핑해야 합니다.

</details>

<details>

<summary>상품 이미지 등록 규격은 어떻게 되나요?</summary>

상품은 배경 포함 514x514px 사이즈를 사용해야 합니다.

</details>

<details>

<summary>판매 등록 후 가격이나 통화를 수정할 수 있나요?</summary>

불가능합니다. 가격이나 구성의 변경이 필요한 경우 새로운 판매 등록을 해야 합니다.

</details>

<details>

<summary>limitPurchaseCount, periodicType, resetAt은 어떻게 작동하나요?</summary>

* limitPurchaseCount: 1 & periodicType: null & resetAt: null:  계정당 최초 1회 구매 가능
* limitPurchaseCount: 1 & periodicType: is not null & resetAt: is not null:  기간마다 1회 구매 가능하고, 기간 도래 시 구매 가능 개수 초기화
* limitPurchaseCount: null: 구매 제한 없음

</details>

<details>

<summary>판매 상품 삭제가 가능한가요?</summary>

판매가 시작되거나 판매 이력이 있는 상품은 삭제가 불가능합니다. 단, 판매가 시작되지 않은 경우는 삭제가 가능합니다.

</details>

<details>

<summary>판매 등록 요청 후 saleId는 어떻게 확인하나요?</summary>

판매 등록 후 반환되는 id가 saleId 입니다.

</details>

<details>

<summary>패키지 상품의 수량 표기 / 지급 수량은 어느 값을 기반으로 하나요?</summary>

subItemList.amount 값을 기반으로 노출됩니다.

</details>

<details>

<summary>섹션 등록은 뭔가요?</summary>

B2C 상품을 진열할 섹션 리스트가 필요하며, 1개만 있다면 단일 컬럼, 2개 이상이면 웹샵 상단 탭과 앵커가 동작됩니다.

</details>

## 결제

<details>

<summary>지원되는 통화는 무엇인가요?</summary>

Fiat 결제로는 USD, JPY, THB, PHP, IDR, TWD, KRW를 지원하며, Crypto 결제로는 USDt를 지원합니다.

미지원 통화의 경우에는 USD로 결제 가능합니다.

</details>

<details>

<summary>실결제 테스트는 어떻게 진행하나요?</summary>

Preview 환경에서는 가상 결제가 이루어지고, Prod 환경에서는 실제 신용카드 결제 (international creditcard 결제로만 테스트)가 필요합니다.

</details>

<details>

<summary>multiCurrencyPrice 동작 방식은 어떻게 되나요?</summary>

국가별 설정된 로컬 통화가 우선 적용되며, 해당 통화가 없는 경우는 USD로 표시됩니다.

</details>

<details>

<summary>multiCurrencyPrice를 0으로 설정하면 어떻게 되나요?</summary>

무료 구매로 처리됩니다.

</details>

<details>

<summary>통화별 최소 결제 금액은 어떻게 되나요?</summary>

통화별 최소 결제 금액

* USD: 0.01
* JPY: 1
* THB: 1
* PHP: 6
* IDR: 1,000
* TWD: 30
* KRW: 10

B2C 상품의 최저 가격은 통화별 최소 결제 금액 이상으로 설정되어야 하므로, 가격 확정 전 LINE NEXT와의 협의가 필요합니다.

</details>

## 배송

<details>

<summary>배송 요청 시 requestId 형식은 어떻게 되나요?</summary>

UUID 형식이 아니어도 되며, 특정 prefix를 포함할 수 있습니다. 다만 모든 요청마다 유니크해야 합니다.

</details>

<details>

<summary>동일 요청이 중복으로 발생한 경우에는 어떻게 처리되나요?</summary>

유일성을 보장하고 있어 동일 요청이 중복으로 발생되더라도 requestId가 동일하므로 중복 요청으로 인지하고 거부하시면 됩니다.

</details>

<details>

<summary>requestId로 구매이력을 확인할 수 있나요?</summary>

배송 요청의 식별키로만 사용하고 있고, 서버 간 요청의 결과를 확인하는데 사용할 수는 있지만 구매이력 등 별도의 조회를 위한 식별키로는 활용이 불가능함

</details>

<details>

<summary>결제 성공 후 배송 요청 지연되는 경우가 있나요?</summary>

동시 구매량 등에 따른 배송 지연 가능성은 있지만 재처리 프로세스가 존재하여 이슈는 없습니다.

</details>

<details>

<summary>배송 이력 조회 관련해서 배송을 못받는 경우는 acquiredAt이 0으로 확인되나요?</summary>

acquiredAt은 배송 완료 시점을 의미하기 때문에 항상 값이 있습니다. 만약 배송 실패가 발생한다면 조회 결과 값이 없으므로 이런 경우는 비정상 배송건으로 판단이 필요합니다.

</details>

## 환불

<details>

<summary>환불은 어떻게 처리되나요?</summary>

환불은 유저 요청 → 개발사가 아이템 회수 → 정산 검토 후 환불 처리 결정 → PG사를 통한 환불 순서로 진행되며, 모든 환불은 수동으로 처리됩니다.

</details>

<details>

<summary>환불 안내 문구는 어떻게 적용되나요?</summary>

웹샵의 안내 문구에서만 국가별로 조정할 수 있으며, 인게임에서는 일관성을 위해 환불 불가 정책 문구를 사용합니다.

</details>

<details>

<summary>Prod 환경에서 결제 테스트는 환불이 가능한가요?</summary>

네 가능합니다. 다만, Prod 환경에서 결제 / 취소 시 PG사 수수료가 발생하므로 개발사, NEXT 양사에서 취소 수수료를 부담하는 것으로 진행하고 있습니다.

* 유의사항 및 취소 수수료
  * international creditcard 결제로만 테스트 가능
  * 결제 / 취소 각각 $0.3 + VAT 발생
    * 결제 후 취소 시 $0.66 발생
  * 계약 상 수수료는 다음달 정산에서 차감처리 예정 → 개발사, NEXT 공동 부담

</details>

## 정산

<details>

<summary>정산은 어떻게 진행되나요?</summary>

매출 정산 대상은 월별로 집계하고 있습니다. 타임라인 공유드립니다.

* 매출 집계 및 검증: 익월 3영업일
* Biz Report 제공: 익월 4 \~ 5 영업일
* 정산 지시: 익월 20일
* 정산금 지급: 익월 21일

</details>

## 미션&리워드

<details>

<summary>미션 등록 후 확인이 불가능 경우는?</summary>

개발사에서 미션 등록 후에 NEXT Market에서 보상 및 공개 시각을 추가로 설정해야 하며, 설정 완료된 이후에 공개 시각 시점에 노출됩니다.

</details>

<details>

<summary>캐릭터 단위로 미션 달성 여부를 확인할 수 있나요?</summary>

게임에 따라 게임의 계정 또는 캐릭터 단위로 미션 달성 상태가 관리됩니다.

단, 캐릭터 단위 확인이 필요하다면 캐릭터 단위 GUID를 별도로 생성해야 하며, 이는 NEXT Market과 설정 협의가 필요합니다.

</details>

<details>

<summary>미션 달성 확인과 사용자 보상 수령의 Flow는 어떻게 진행되나요?</summary>

[Flow 확인하러가기](https://github.com/tech-support-trade/docs/wiki/%EB%AF%B8%EC%85%98-%EB%8B%AC%EC%84%B1-%ED%99%95%EC%9D%B8%EA%B3%BC-%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%B3%B4%EC%83%81-%EC%88%98%EB%A0%B9)

</details>

<details>

<summary>모바일/패드 환경에서 미션 참여 버튼이 비노출 처리되는 이유는 무엇인가요?</summary>

미션 페이지의 기본 참여 버튼은 외부 페이지로 연결되며, 웹뷰 환경에서는 앱 이탈을 방지하기 위해 비노출 처리됩니다. 미션을 달성하거나 이후 과정을 완료한 경우에는 보상 버튼 또는 보상 지급 완료 버튼이 정상적으로 노출됩니다.

PC 환경에서는 노출처리되며, 모바일 / 패드 환경 한정에서만 위와 같이 노출되고 있습니다.

</details>

<details>

<summary>missionType은 어떤 것이 있나요?</summary>

* SINGLE: 정해진 목표를 달성하면 종료되며, 달성 후 리셋됩니다.
* ACCUMULATE: 누적 수치가 계속 쌓이는 방식입니다.
  * 예) 20/20 완료 후 40 달성 시 40/40으로 처리
* DIFFICULTY: 회차마다 목표치와 난이도가 증가합니다. 달성 후에는 다시 0부터 시작합니다.
  * 예) 1회차 20마리 처치(0/20) → 2회차 40마리 처치(0/40)
* CHALLENGE: 진행 중인 미션들을 컬렉션으로 설정하여 지정한 미션들이 모두 달성되어야 같이 달성이 되어 보상받을 수 있게 됩니다.

</details>

## 웹샵

<details>

<summary>웹샵 언어 노출 기준은 무엇인가요?</summary>

우선순위는 다음과 같습니다.

* NEXT Market 제공하는 5개 언어 중, 웹샵에서 지원할 언어를 선택하고 그중 스토어의 기본 언어를 설정합니다.
  * 제공 언어: English, 한국어, 日本語, 中文（繁體）, ภาษาไทย
* 비로그인 유저: 스토어 기본 언어
* 로그인 유저: 유저가 설정한 언어 또는 유저가 푸터에서 설정한 언어
  * 단, 유저의 브라우저 / OS에서 설정한 언어가 NEXT Market에서 제공하는 언어가 아닌 경우 스토어 기본 언어로 노출

</details>

<details>

<summary>Prod 환경에서 발급한 토큰으로 Preview 환경에 붙여서 열면 Prod 웹샵이 뜨나요?</summary>

Preview와 Prod는 완전히 독립 환경이라 인증이 되지 않습니다. Prod용 웹샵 도메인은 따로 있습니다.

</details>

## Webview

<details>

<summary> NEXT Market을 인게임 Webview로 제공하는 방법은?</summary>

NEXT Market을 인게임 Webview로 제공할 계획인 경우, LINE NEXT 측으로 사전 안내가 필요합니다.

자세한 내용은 다음 가이드 문서 참고 부탁드립니다. ([가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-8#market-webview))

</details>

## 테스트

<details>

<summary>Preview 테스트 간 주의사항이 있나요?</summary>

Preview 스토어는 일반 사용자에게도 공개될 수 있는 페이지로, 실제 상품이나 아이템, 가격 등 일반 사용자에게 미리 공개되면 안되는 항목은 입력되지 않도록 주의가 필요합니다.

</details>

<details>

<summary>Preview 테스트 시 어떤 항목을 확인해야 할까요?</summary>

게임 <> 웹샵 이동 시 동선 (Webview 또는 외부 브라우저), 로그인 동작, 상품 구매 후 아이템 배송 중심으로 확인하는 것을 권장합니다.

테스트 진행 중 이슈 발견 시 대응을 위해 웹샵 오픈 3영업일 전에는 위 항목들에 대한 테스트를 부탁드립니다.

</details>

<details>

<summary>Preview 환경에서 점검모드를 설정하는 이유가 있나요?</summary>

Preview 환경에서 접근성을 높이며, 일반 사용자가 공개되지 않은 스토어에 접근하는 문제를 해결하기 위해 점검모드 설정 후 테스트를 진행하고 있습니다. Prod 오픈 시점에도 동일한 방식으로 점검모드 후 테스트 진행하고 있는 점 참고 부탁드립니다.

자세한 내용은 다음 가이드 문서 참고 부탁드립니다. ([가이드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-8#market))

</details>

<details>

<summary>기존 TWD만 등록한 상품 대상으로 USD, JPY 등 다른 통화로 테스트하고 싶은 경우는 어떻게 해야 하나요?</summary>

상품을 새로 등록하신 후 테스트 진행하셔야 합니다. 단, 부득이한 경우에는 LINE NEXT와 협의 후 테스트 지원은 가능한 점 참고 부탁드립니다.

</details>

## 정책

<details>

<summary>게임 계정이 제재된 경우에도 NEXT Market을 이용할 수 있나요?</summary>

불가능합니다. NEXT Market은 게임 로그인 이후에만 접근할 수 있으므로, 게임 계정이 제재된 상태에서는 이용할 수 없습니다. 단, 단순 아이템 목록 조회는 가능할 수 있습니다.

</details>
