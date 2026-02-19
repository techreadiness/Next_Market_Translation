metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/mission-management
---

# Mission Management

The Mission Management page allows you to create missions and manage their operational status.

* Features Provided
  * [Create Mission](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#post-api-v1-incentive-mission)
  * [Edit Mission](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-7#put-api-v1-incentive-mission-missionid)

⚠️ Important Notes

* Please register missions only after prior consultation with LINE NEXT.
* Mission management does not support CSV upload functionality. All missions must be registered individually via the Console.
* Registered missions will only be displayed on NEXT Market. If you wish your mission to appear on the Dapp Portal USDt Rewards section, please make a separate request to your NEXT business manager.
  * Note: For Dapp Portal USDt Rewards exposure, a separate logo image (420x420px) must be submitted.

## Mission Creation

Mission creation is the function to register and manage missions.

{% stepper %}
{% step %}
### Select the Mission Management Page

* Access the NEXT Market Console
* Select the **Mission Management** page from the left menu
{% endstep %}

{% step %}
### Create a Mission

* Select the Create Mission button to proceed to the registration screen.

<figure><img src="../../.gitbook/assets/미션 관리_생성.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter Basic Information

Enter the mission&#x27;s basic information.

| Field    | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Event Key    | <ul><li><p>Unique key value for identifying the mission</p><ul><li>Can be set via vendor designation or auto-generation</li></ul></li><li>Format: Character limit of 3 to 36 characters; only letters, numbers, and underscores allowed <code>_</code> only</li></ul><p>⚠️ The Event Key is the basis for distinguishing missions; please manage it to avoid duplication.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Mission Type    | <ul><li><p>Set the mission completion method and reward distribution criteria</p><ul><li>The achievement conditions and round mechanics vary depending on the selected mission type.</li></ul></li><li><p>SINGLE</p><ul><li>Achieved by completing a single objective, with rewards obtained upon each completion</li><li>If rounds are specified, it resets after each round.</li></ul></li><li><p>ACCUMULATE</p><ul><li>Achieve cumulative goals; reach a set threshold to earn rewards.</li><li>For designated rounds, the cumulative achievement amount increases while maintaining the previous achievement value.</li></ul></li><li><p>DIFFICULTY</p><ul><li>Mission difficulty can be set to change per mission.</li><li>If the chapter and difficulty settings do not match, the difficulty reverts to the initial setting.</li></ul></li><li><p>CHALLENGE</p><ul><li>Set ongoing missions as a collection; all designated missions must be completed together to achieve the collection and obtain rewards.</li></ul></li><li>The mission creation API <code>missionType</code> Passed as a value</li></ul> |
| Round      | <ul><li>Sets the mission&#x27;s repetition count</li><li>If no iteration is specified, the mission is defined as infinite.</li><li>Specifying the iteration number initializes conditions corresponding to the mission type according to the format or changes the achievement criteria.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Realm Code | <ul><li><p>Used when mission execution is conducted per Realm (game server)</p><ul><li>Used only when mission operation is required for specific servers or environments.</li></ul></li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

<figure><img src="../../.gitbook/assets/미션 관리_기본정보.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Multilingual Information Input

Enter the mission name and mission description.

| Field | Value                                                                                                                         |
| ----- | ----------------------------------------------------------------------------------------------------------------------------- |
| Mission Name   | <ul><li>Supports multilingual input: en, ko, ja, th, zh</li><li>Value displayed as the mission name on the Mission &amp; Rewards page</li><li>Must be registered for languages provided by the marketplace</li></ul>   |
| Mission Description | <ul><li>Multilingual Input Support: en, ko, ja, th, zh</li><li>Value displayed as the mission description on the Mission &amp; Rewards page</li><li>Must be registered for all languages provided by the marketplace</li></ul> |

<figure><img src="../../.gitbook/assets/미션 관리_다국어 정보.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter Achievement Goals

* Enter achievement goals based on the mission type.
* The required achievement goal values vary depending on the mission type settings.

| Mission Type      | Field      | Value                                                                                                                |
| ---------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| SINGLE     | Number of completions    | <ul><li>Enter the number of times the mission was completed for single-goal missions</li></ul>                                                                         |
| ACCUMULATE | Cumulative Achievement Count | <ul><li>Enter the total number of times the cumulative mission has been completed</li></ul>                                                                   |
| DIFFICULTY | Difficulty Level   | <ul><li>Set difficulty levels for missions to change per attempt</li><li><p>Format</p><ul><li>Enter comma-separated difficulty values</li><li>Example) 1,2,3,4</li></ul></li></ul> |
| CHALLENGE  | Associated Mission IDs | <ul><li>Enter the mission IDs of missions to be collected</li><li><p>Format</p><ul><li>Enter mission ID values separated by commas</li><li>Example) 1,2,3,4</li></ul></li></ul>      |
{% endstep %}

{% step %}
### Enter Operation Period

* Enter the mission&#x27;s operation period.
* Format: yyyy-MM-dd HH:mm (UTC+9)
{% endstep %}

{% step %}
### Enter Media Information

* Register only if the mission&#x27;s reward type is an item.

⚠️ Image upload is not required for USDt rewards.

* Upload Method
  * URL Input: Enter the URL of an already uploaded media file
  * File Upload: Select and upload a local file
* Supported Formats
  * IMAGE: JPG, PNG, WebP
* Upload Limits
  * File Size: 10MB or less
  * Image Size: 72x72px including background

⚠️ VIDEO format upload is functionally selectable, but **since it is not officially supported, please register only in IMAGE format.**

<figure><img src="../../.gitbook/assets/미션 관리_미디어 정보.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Device Link Input

* Enter the URL to redirect to when the \[Participate] button is selected for each environment&#x27;s mission.

<figure><img src="../../.gitbook/assets/미션 관리_디바이스 링크.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Enter Country Restrictions

* Set the mission&#x27;s country-specific access restriction policy.
*   Select restricted country access option

    * No Control
    * Whitelist / Target Countries
    * Blacklist / Target Countries

    ⚠️ Whitelist and Blacklist **cannot be applied simultaneously. Target countries** must be entered using the list of country codes expressed as ISO 3166-1 alpha-2 two-letter uppercase codes.

<figure><img src="../../.gitbook/assets/미션 관리_국가 제어.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## Mission Modification

Mission modification is a feature used **when you need to change the information of an already registered mission**.

* Access **NEXT Market Console**
* Select the **Mission Management** page from the left menu
* Choose the mission to edit from the mission information list
* Click the **Edit** button
* Save after modifying the mission information

<figure><img src="../../.gitbook/assets/미션 관리_수정.png" alt=""><figcaption></figcaption></figure>

### ⚠️  Important Notes When Editing

*   You cannot edit missions that are currently in progress.
*   You can edit missions before their start date, but you cannot change the mission type.
    *   If you need to change the mission type, you must register a new mission.

## Additional Submission Information Guide

*   To set up a mission, you need to submit additional information beyond what you registered via the API and Console.
  * Please review the information below and submit it to LINE NEXT.
  * Information submission is done by completing and submitting an Excel template.

### Banner Information

This submission item is for setting **banner information displayed at the top of the Mission &amp; Reward page** in the Market.

| Field       | Value                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Main Image      | <ul><li>Submit 2 images (PC / Mobile)</li><li><p>Supported formats</p><ul><li>IMAGE: JPG, PNG, WebP</li></ul></li><li><p>Image Size</p><ul><li>PC: 1200x360px</li><li>Mobile: 810x160px</li></ul><h3> </h3></li></ul><p>⚠️ Important Notes</p><ul><li>For Retina (high-resolution) display compatibility, please <strong>create images at twice the recommended resolution</strong>.</li><li>For mobile images, the left and right areas may be cropped depending on the device resolution. We recommend placing key content so it is not centered to the left or right.</li></ul> |
| Logo Image      | <ul><li><p>Supported formats</p><ul><li>IMAGE: JPG, PNG, WebP</li></ul></li><li>Image Size: 478x100px</li></ul><p>⚠️ Important Notes</p><ul><li>The vertical height is fixed at 100px, and the horizontal width can be created up to a maximum of 478px.</li><li>Please ensure there are no margins on the left or right sides of the image.</li></ul>                                                                                                                                                                  |
| Mission &amp; Reward Description | <ul><li>Multilingual Input Support: en, ko, ja, th, zh</li><li>Must be registered for languages provided by the Market</li></ul>                                                                                                                                                                                                                                                                                                     |

<figure><img src="../../.gitbook/assets/배너.png" alt=""><figcaption></figcaption></figure>

### Mission Rewards

Mission reward settings are only possible via LINE NEXT.

| Field | Value                                                                                    |
| ----- | ---------------------------------------------------------------------------------------- |
| Reward Type | <ul><li><p>Select Reward Type</p><ul><li>USDt</li><li>SKU</li></ul></li></ul>                      |
| Reward Target | <ul><li><p>Enter Reward Quantity</p><ul><li>USD: Enter quantity only</li><li>SKU: Enter SKU and quantity</li></ul></li></ul>   |
| Total Limit  | <ul><li><p>Enter the total budget allocated to the mission</p><ul><li>USDt: Enter quantity</li><li>SKU: Enter the number of items</li></ul></li></ul> |
