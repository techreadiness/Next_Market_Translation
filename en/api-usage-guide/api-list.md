# API List

## Game ➡️ Next Market

### Authentication and Security 

* [Check Server Time](authentication-security.md#post-api-v1-server-time)
* [Request One-Time Token for Store Authentication](authentication-security.md#post-api-v1-auth-token)
* [Delete Store Session](authentication-security.md#delete-api-v1-account-session-kick)

### B2C Item Registration

{% stepper %}
{% step %}
#### Item Requests

* [Media File Upload](item.md#post-api-v1-media-upload)
* [Item Registration](item.md#post-api-v1-item)
* [Item Update](item.md#put-api-v1-item-sku)
* [Item Query](item.md#get-api-v1-item-sku)
* [Item List Query](item.md#get-api-v1-item)
{% endstep %}

{% step %}
#### Section Request

* [Register Section](section.md#post-api-v1-sale-b2c-section)
* [Update Section](section.md#patch-api-v1-sale-b2c-section-sectionid)
* [Get Section List](section.md#get-api-v1-sale-b2c-section)
{% endstep %}

{% step %}
#### Sales Request

* [Register Sale](sale.md#post-api-v1-sale-b2c)
* [Update Sale](sale.md#patch-api-v1-sale-b2c-b2csaleid)
* [Get Sales List](sale.md#get-api-v1-sale-b2c)
{% endstep %}
{% endstepper %}

### B2C Item Sales

* [Request One-Time Token](authentication-security.md#post-api-v1-auth-token)
* [View Sales Statistics](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#get-api-v1-sale-b2c-statistics)
* [Register a Sale](sale.md#post-api-v1-sale-b2c)
* [Modify Sale](sale.md#patch-api-v1-sale-b2c-b2csaleid)
* [Get Sale List](sale.md#get-api-v1-sale-b2c)
* [Delete B2C Sale](sale.md#delete-api-v1-sale-b2c-b2csaleid)

### C2C Item Registration

* [Media File Upload](item.md#post-api-v1-media-upload)
* [Item Registration](item.md#post-api-v1-item)
* [Item Ability Setting Registration](item.md#post-api-v1-item-ability)
* [Modify Item Ability Settings](item.md#put-api-v1-item-ability-code)
* [Retrieve Item Ability Settings List](item.md#get-api-v1-item-ability)

### C2C Item Sales

* [Request One-Time Token](authentication-security.md#post-api-v1-auth-token)
* [Retrieve Item Shipping History](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#get-users-api-v1-item-send-item-guid-guid)
* [Cancel C2C Item Sale](sale.md#delete-api-v1-sale-c2c-c2csaleid)

### Settlement

* [Sales Data Inquiry](settlement.md#get-api-v1-settlement)

### Mission

* [Mission Creation](mission.md#post-api-v1-incentive-mission)
* [Mission Modification](mission.md#put-api-v1-incentive-mission-missionid)
* [Delete Mission](mission.md#delete-api-v1-incentive-mission-missionid)
* [Request Achievement Record](mission.md#post-api-v1-incentive-mission-achieve)
* [Get Mission Board](mission.md#get-api-v1-incentive-mission)



Next Market➡️ Game

B2C Item Purchase

* [Account Status Inquiry](account.md#undefined)
* [Item Delivery](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined)
* [Item Delivery Status Inquiry](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-2)

### C2C Item Purchase

* [Sealing](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-4)
* [Unsealing](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-6)
* [Account Status Check](account.md#undefined)
* [Item Exchange](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-8)
* [Item Exchange Verification](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#undefined-10)

### Account

* [Game Account Status Inquiry](account.md#undefined)
