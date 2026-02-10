---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/firewall-configuration
---

# 방화벽 해제 설정

NEXT Market과 Game은 양방향 API 통신이 필요하며, NEXT Market은 Inbound, Outbound 모두 방화벽 정책 해제 설정이 필요합니다. 아래 표에 기재된 정보를 NEXT Market 측으로 전달해주시면 Store 개설 후 방화벽 해제를 진행한뒤, API 연동을 위한 Key 정보를 게임사 측으로 전달합니다.&#x20;

| Environment | Direction                     | Source                                                                                                                                                                         | Destination                                                           |
| ----------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Preview     | <p>NEXT Market<br>-> Game</p> | <p>147.92.141.97<br>147.92.141.98<br>147.92.141.99<br>147.92.141.100<br>147.92.234.208<br>147.92.234.209<br>147.92.234.220<br>147.92.173.222</p>                               | <mark style="color:blue;">**게임 측 서버 도메인 또는 IP와 포트 정보**</mark>         |
|             | <p>Game<br>-> NEXT Market</p> | <mark style="color:blue;">**IP Address 목록**</mark>                                                                                                                             | [https://app-sdk.nextmarket.games​](https://app-sdk.nextmarket.games) |
| Production  | <p>NEXT Market<br>-> Game</p> | <p>147.92.139.225<br>147.92.139.226<br>147.92.139.227<br>147.92.139.228<br>147.92.235.249<br>147.92.235.30<br>147.92.238.90<br>147.92.238.95<br>43.223.9.34<br>43.223.9.42</p> | <mark style="color:blue;">**게임 측 서버 도메인 또는 IP와 포트 정보**</mark>         |
|             | <p>Game<br>-> NEXT Market</p> | <mark style="color:blue;">**IP Address 목록**</mark>                                                                                                                             | [https://sdk.nextmarket.games​](https://sdk.nextmarket.games)         |

* <mark style="color:blue;">**Game 측에서 NEXT Market 측으로 제공이 필요한 정보 (Preview, Production 환경 별로 제공)**</mark>
  * NEXT Market에서 게임 측에 호출할 서버 도메인 또는 IP와 포트 정보 (Destination)
  * Game 측에서 NEXT Market으로 호출할 때 사용되는 출발 IP (Source)
* Game 측에서 설정이 필요한 정보 (네트워크 설정 필요 시)
  * NEXT Market 측에서 Game 호출 시 사용하는 출발 IP (Source)
  * Game 측에서 호출할 NEXT Market의 API Endpoint (Destination)
