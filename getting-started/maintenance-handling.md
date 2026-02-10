---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/maintenance-handling
---

# 점검 상황 대응 가이드

### Market 테스트를 위한 점검우회 방안

#### 기본 정책

LINE NEXT 측에서 Market 설정 및 개설을 완료하면, Market 오픈 전까지 외부에서 접근할 수 없도록 점검모드로 유지합니다. 게임 개발사는 LINE NEXT에서 제공하는 점검우회 URL을 사용하여 접근할 수 있습니다. 점검우회 URL 확인이 필요하신 경우, 담당자에게 요청해주세요.

#### Webview로 테스트하고자 하는 경우

API 요청 시  점검우회 URL에서 확인할 수 있는 Cookie 값을 header에 추가해주시면 됩니다.

```
key: MAINTENANNCE_COOKIE
value: xxxxxxx-....
```

점검우회 URL이 변경되면 value도 변경될 수 있으니, run-time으로 설정이 필요합니다.
