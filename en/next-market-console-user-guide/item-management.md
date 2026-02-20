metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/item-management
---

# Item Management

The Item Management page allows you to register and manage items used in B2C and C2C transactions.

This page provides the item registration API functionality within the Console environment.

* Provided Functions
  * [미디어 파일 업로드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-media-upload)
  * [아이템 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item)
  * [아이템 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-sku)
  ## Item Registration (Individual Registration)

Item registration supports the **individual registration method**.
When registering a small number of items, you can create them through individual registration.

{% stepper %}
{% step %}
### Select the Item Management Page

* Access NEXT Market Console
* Select the **Item Management** page from the left menu
{% endstep %}

{% step %}
### Select Item Registration

* Select the Item Registration button to proceed to the item registration screen.

<figure><img src="../../.gitbook/assets/아이템 관리_아이템 등록.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Upload Media Files

* Upload media files to be used with the item.

#### Upload Methods

* URL Input: Enter the URL of an already uploaded media file
* File Upload: Select a local file and upload it

#### Supported Formats

* IMAGE: JPG, PNG, WebP

⚠️ VIDEO format upload is functionally possible, but **it is not officially supported. Please register only in IMAGE format.**

#### Upload Restrictions

* File size: 10MB or less
* Image size: 72x72px including background

<figure><img src="../../.gitbook/assets/아이템 관리_미디어 파일 업로드.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter Basic Information

Enter the item&#x27;s basic information.

| Field             | Value                                                                                                                                                                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SKU (Required)    | <ul><li>Unique item code for identifying and managing the item</li><li>Cannot be duplicated</li><li><p>Format: User-guessable value under 200 characters; alphanumeric and special characters allowed</p><ul><li>Special character: underscore only <code>_</code> Hyphen use is recommended <code>-</code>  Use of hyphens is recommended</li></ul><p>⚠️ Please enter the SKU as the exact value used to identify the item in the actual game.</p></li></ul> |
| Item Name (Required) | <ul><li>Multilingual input supported: en, ko, ja, th, zh</li><li><p>Value displayed on item list and detail screens</p><ul><li>Must be registered for languages provided by the Market</li></ul></li></ul>                                                                                                                                  |
| Item Description (Required) | <ul><li>Set as the item name on the item registration page</li><li>If a detailed description is needed, register separately via <strong>CSV upload</strong></li></ul>                                                                                                                                                        |

<figure><img src="../../.gitbook/assets/아이템 등록_기본정보.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Package Item Registration (Optional)

* Select and configure if the item is a package item.

⚠️ **Sub-items included in a package item must be pre-registered.**

| Field     | Value                                    |
| --------- | ---------------------------------------- |
| Sub-item SKU | <ul><li>Enter the SKU of the package item&#x27;s component item</li></ul> |
| Quantity        | <ul><li>Enter the quantity of the sub-item</li></ul>          |

<figure><img src="../../.gitbook/assets/아이템 등록_서브아이템.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### C2C Sales Item Registration (Optional)

* Select and configure if the item is used for C2C transactions.

⚠️ When registering C2C sales items, this field is for entering attributes per item (SKU). It can be used to display item attributes and verify conditions during C2C transactions.

| Field        | Value                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| Capability Name        | <ul><li>Multilingual Input Support: en, ko, ja, th, zh</li><li>Ability Display Name</li><li>Must be registered for languages provided in the Market</li></ul>                                                                                                                                                                                                                                                                                                                         |
| Option Type        | <ul><li>Defines the nature of the information the ability value represents</li><li><p>Select Option Type</p><ul><li>Base Stat (<code>BASIC</code>): Basic Ability</li><li>Constraint Option (<code>CONSTRAINT</code>): Constraints that are added or modified by changes</li><li>Item Quantity (<code>AMOUNT</code>): Value representing the quantity contained within the item</li></ul></li><li>Item Registration API&#x27;s <code>abilties.optionType</code> Passed as a value</li></ul><p>⚠️ <strong>We recommend registering base attributes that do not vary per item together with the SKU during registration</strong> on the Item Management page<strong>.</strong></p> |
| Display Format        | <ul><li>Set <strong>how</strong> the ability value <strong>is displayed to the user</strong></li><li><p>Display Format Selection</p><ul><li>Numeric Value (<code>NONE</code>): Display the entered value as-is</li><li>100% (<code>PPERCENTAGE</code>)</li><li>+100 (<code>NUMERIC</code>)</li><li>100Lv (<code>LEVEL</code>)</li></ul></li><li>Item Registration API <code>abilties.unitType</code> | Value            |</li></ul>                                                                                                    |
| Value            | <ul><li>Input in Decimal format</li><li>Displayed on screen according to the set option type and display format</li><li>Item Registration API&#x27;s <code>abilties.value</code> | | Value            |</li></ul>                                                                                                                                                                                                                                                                                               |
| Country Access Restriction Settings  | <ul><li>Set country-specific access restriction policies for C2C items</li><li><p>Select restricted country access option</p><ul><li>No Restrictions</li><li>Whitelist (<code>policies.whitelist</code>)</li><li>Blacklist (<code>policies.blacklist</code>)</li><li>Note: Whitelist and Blacklist <strong>cannot be applied simultaneously</strong></li></ul></li></ul>                                                                                                                                                                      |
| Minimum Price (USDt) | <ul><li><p>Policy restricting the minimum selling price of C2C items</p><ul><li>C2C listings cannot be registered at prices lower than the set minimum price</li></ul></li><li><code>policies.minPrice</code></li></ul>                                                                                                                                                                                                                                                                                  |

<figure><img src="../../.gitbook/assets/아이템 등록_C2C.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## Item Registration (Bulk Registration)

Bulk item registration is a feature that allows you to register multiple items at once via CSV file upload when you need to register a large number of items simultaneously.

{% stepper %}
{% step %}
### Select the Item Management Page

* Access NEXT Market Console
* Select the **Item Management** page from the left menu
{% endstep %}

{% step %}
### Download Template

* Select the **Download Template** button to download the **CSV template file** for bulk item registration.
* The template includes the basic columns required for item registration.

<figure><img src="../../.gitbook/assets/아이템 관리_템플릿.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Create the Item List

* Enter the information for the items you want to register into the downloaded **CSV template file**.
* Refer to the **Item Registration (Individual Registration)** guide for how to fill out each field.
* Note: For the imageUrl field, only URLs of already uploaded media files are supported; file uploads are not permitted.

⚠️ Uploads may fail if required fields are missing or formatted incorrectly.

<figure><img src="../../.gitbook/assets/아이템 관리_csv 템플릿.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### CSV Upload

* Select and upload the completed CSV file.
* After selecting the file, click the **Upload** button to proceed with bulk item registration.

#### ⚠️ Important Notes for Bulk Registration

* CSV upload is used for **registering new items or modifying existing registered item information**.
* We recommend performing a **small-scale test upload** before registering via CSV upload.

<figure><img src="../../.gitbook/assets/아이템 관리_csv 업로드.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## Item Modification

Item modification is a feature used **when you need to change information for already registered items**.
NEXT Market Console provides two methods for item modification: **individual modification** and **bulk modification**.

### Item Modification Methods

#### Individual Modification

Use this when modifying the information of a single item.

* Access **NEXT Market Console**
* Select the **Item Management** page from the left menu
* Select the item to modify from the item list
* Click the **Modify** button
* Change the item information and save

<figure><img src="../../.gitbook/assets/아이템 관리_수정.png" alt=""><figcaption></figcaption></figure>#### Bulk Editing

Use this when you need to modify the information for multiple items at once.

* Select the **CSV Download** button on the **Item Management** page
* Change the item information to be modified in the downloaded CSV file
* Upload the modified CSV file
* Review the modification results after upload is complete

<figure><img src="../../.gitbook/assets/아이템 관리_csv 다운로드.png" alt=""><figcaption></figcaption></figure>### ⚠️  Important Notes When Editing

* Changing information for items currently on sale may impact service operations.
* We recommend performing a **small-scale test edit** before bulk editing.
