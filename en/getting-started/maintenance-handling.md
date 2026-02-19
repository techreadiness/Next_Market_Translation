metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/maintenance-handling
---

# Maintenance Response Guide

### Workaround for Market Testing

#### Basic Policy

Once LINE NEXT completes Market setup and launch, it remains in maintenance mode until the official Market opening, preventing external access. Game developers can access it using the maintenance bypass URL provided by LINE NEXT. If you need to confirm the bypass URL, please request it from your assigned contact.

#### For Testing via Webview

When making API requests, add the Cookie value found in the maintenance bypass URL to the header.

```
key: MAINTENANNCE_COOKIE
value: xxxxxxx-....
```

The value may change if the maintenance bypass URL is updated, so runtime configuration is required.
