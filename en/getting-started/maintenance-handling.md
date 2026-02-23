---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/maintenance-handling
---


# Maintenance Response Guide

### Workaround for Market Testing

#### Basic Policy

Once LINE NEXT completes Market setup and launch, it remains in maintenance mode until the Market opens, preventing external access. Game developers can access it using the maintenance bypass URL provided by LINE NEXT. If you need to confirm the maintenance bypass URL, please request it from your assigned contact.

#### For Testing via Webview

When making API requests, add the Cookie value found in the bypass URL to the header.

```
key: MAINTENANNCE_COOKIE
value: xxxxxxx-....
```

The value may change if the bypass URL is updated, so runtime configuration is required.
