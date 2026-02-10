---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/in-game-webview-guide
---

# 인게임 Webview 제공

### Market을 인게임 WebView로 제공하는 경우

Market을 인게임 WebView로 제공할 계획인 경우, LINE NEXT 측으로 사전 안내가 필요합니다.

#### Webview 가이드

* Market 이동 시 inapp=true param 추가&#x20;
* 참고 예시

```
<a href="https://{store domain}/auth?token={one time token}&inapp=true" target="_blank">무료 아이템 받기</a>
```

* 웹 페이지 내 새 창으로 페이지가 열리는 경우, 외부 브라우저로 열어주세요.
  * WebView에서는 새 창이 불가합니다.
  * 웹페이지에서 새 창이 외부 브라우저로 열리도록 설정해주세요.
    * `<a target="`_`blank">...</a>` 또는 `window.open(..., "`_`blank")`
  * 참고 문서: [UniWebView - Supporting New Window](https://docs.uniwebview.com/guide/support-new-window.html)

{% hint style="warning" %}
**Viewplex Webview 사용 시 주의사항**\
Viewplex Webview를 사용하는 경우, 기본 동작은 모든 URL을 현재 WebView 내에서 여는 것입니다.\
결제 진행을 위해서는 새 창으로 페이지를 열어야 하므로, <mark style="color:red;">새 창 이벤트를 감지하여 별도로 처리하는 구현이 필요합니다.</mark>

새 창 이벤트 감지를 위해 Vuplex의 [IWithPopups Interface](https://developer.vuplex.com/webview/IWithPopups) 를 사용하실 수 있습니다.\
해당 인터페이스를 활용하여 새 창 요청 시 외부 브라우저를 열도록 처리해주세요.
{% endhint %}

* 웹뷰 권장 사이즈&#x20;
  * 게임에서 가려지면 안되는 영역을 제외한 최대한의 사이즈로 권장합니다. 유저가 상품 정보를 확인하거나 결제 정보를 입력할 때 불편함을 최소화하기 위함입니다.&#x20;
  * 최소한으로 보장이 필요한 사이즈는 다음과 같습니다.
    * 가로: 600px&#x20;
    * 세로: 375px&#x20;
