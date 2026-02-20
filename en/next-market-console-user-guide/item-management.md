# item-management

### metaLinks: alternates: - >- https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/item-management

## Item Management

The Item Management page allows you to register and manage items used in B2C and C2C transactions.

This page provides the item registration API functionality within the Console environment.

*   Provided Functions

    * [미디어 파일 업로드](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-media-upload)
    * [아이템 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item)
    * [아이템 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-sku)

    ### Item Registration (Individual Registration)

Item registration supports the **individual registration method**. When registering a small number of items, you can create them through individual registration.

{% stepper %}
{% step %}
#### Select the Item Management Page

* Access NEXT Market Console
* Select the **Item Management** page from the left menu
{% endstep %}

{% step %}
#### Select Item Registration

* Select the Item Registration button to proceed to the item registration screen.
{% endstep %}

{% step %}
#### Upload Media Files

* Upload media files to be used with the item.

**Upload Methods**

* URL Input: Enter the URL of an already uploaded media file
* File Upload: Select a local file and upload it

**Supported Formats**

* IMAGE: JPG, PNG, WebP

⚠️ VIDEO format upload is functionally possible, but **it is not officially supported. Please register only in IMAGE format.**

**Upload Restrictions**

* File size: 10MB or less
* Image size: 72x72px including background
{% endstep %}

{% step %}
#### Enter Basic Information

Enter the item's basic information.

| Field                       | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SKU (Required)              | <ul><li>Unique item code for identifying and managing the item</li><li>Cannot be duplicated</li><li><p>Format: User-guessable value under 200 characters; alphanumeric and special characters allowed</p><ul><li>Special character: underscore only <code>_</code> Hyphen use is recommended <code>-</code> Use of hyphens is recommended</li></ul><p>⚠️ Please enter the SKU as the exact value used to identify the item in the actual game.</p></li></ul> |
| Item Name (Required)        | <ul><li>Multilingual input supported: en, ko, ja, th, zh</li><li><p>Value displayed on item list and detail screens</p><ul><li>Must be registered for languages provided by the Market</li></ul></li></ul>                                                                                                                                                                                                                                                   |
| Item Description (Required) | <ul><li>Set as the item name on the item registration page</li><li>If a detailed description is needed, register separately via <strong>CSV upload</strong></li></ul>                                                                                                                                                                                                                                                                                        |
{% endstep %}

{% step %}
#### Package Item Registration (Optional)

* Select and configure if the item is a package item.

⚠️ **Sub-items included in a package item must be pre-registered.**

| Field        | Value                                                                |
| ------------ | -------------------------------------------------------------------- |
| Sub-item SKU | <ul><li>Enter the SKU of the package item's component item</li></ul> |
| Quantity     | <ul><li>Enter the quantity of the sub-item</li></ul>                 |
{% endstep %}

{% step %}
#### C2C Sales Item Registration (Optional)

* Select and configure if the item is used for C2C transactions.

⚠️ When registering C2C sales items, this field is for entering attributes per item (SKU). It can be used to display item attributes and verify conditions during C2C transactions.

\| Field | Value | | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| Capability Name |

* Multilingual Input Support: en, ko, ja, th, zh
* Ability Display Name
* Must be registered for languages provided in the Market

\| | Option Type |

* Defines the nature of the information the ability value represents
* Select Option Type
  * Base Stat (`BASIC`): Basic Ability
  * Constraint Option (`CONSTRAINT`): Constraints that are added or modified by changes
  * Item Quantity (`AMOUNT`): Value representing the quantity contained within the item
* Item Registration API's `abilties.optionType` Passed as a value

⚠️ **We recommend registering base attributes that do not vary per item together with the SKU during registration** on the Item Management pag&#x65;**.**

\| | Display Format |

* Set **how** the ability value **is displayed to the user**
* Display Format Selection
  * Numeric Value (`NONE`): Display the entered value as-is
  * 100% (`PPERCENTAGE`)
  * +100 (`NUMERIC`)
  * 100Lv (`LEVEL`)
* Item Registration API `abilties.unitType` | Value |

\| | Value |

* Input in Decimal format
* Displayed on screen according to the set option type and display format
* Item Registration API's `abilties.value` | | Value |

\| | Country Access Restriction Settings |

* Set country-specific access restriction policies for C2C items
* Select restricted country access option
  * No Restrictions
  * Whitelist (`policies.whitelist`)
  * Blacklist (`policies.blacklist`)
  * Note: Whitelist and Blacklist **cannot be applied simultaneously**

\| | Minimum Price (USDt) |

* Policy restricting the minimum selling price of C2C items
  * C2C listings cannot be registered at prices lower than the set minimum price
* `policies.minPrice`

|
{% endstep %}
{% endstepper %}

### Item Registration (Bulk Registration)

Bulk item registration is a feature that allows you to register multiple items at once via CSV file upload when you need to register a large number of items simultaneously.

{% stepper %}
{% step %}
#### Select the Item Management Page

* Access NEXT Market Console
* Select the **Item Management** page from the left menu
{% endstep %}

{% step %}
#### Download Template

* Select the **Download Template** button to download the **CSV template file** for bulk item registration.
* The template includes the basic columns required for item registration.
{% endstep %}

{% step %}
#### Create the Item List

* Enter the information for the items you want to register into the downloaded **CSV template file**.
* Refer to the **Item Registration (Individual Registration)** guide for how to fill out each field.
* Note: For the imageUrl field, only URLs of already uploaded media files are supported; file uploads are not permitted.

⚠️ Uploads may fail if required fields are missing or formatted incorrectly.
{% endstep %}

{% step %}
#### CSV Upload

* Select and upload the completed CSV file.
* After selecting the file, click the **Upload** button to proceed with bulk item registration.

**⚠️ Important Notes for Bulk Registration**

* CSV upload is used for **registering new items or modifying existing registered item information**.
* We recommend performing a **small-scale test upload** before registering via CSV upload.
{% endstep %}
{% endstepper %}

### Item Modification

Item modification is a feature used **when you need to change information for already registered items**. NEXT Market Console provides two methods for item modification: **individual modification** and **bulk modification**.

#### Item Modification Methods

**Individual Modification**

Use this when modifying the information of a single item.

* Access **NEXT Market Console**
* Select the **Item Management** page from the left menu
* Select the item to modify from the item list
* Click the **Modify** button
* Change the item information and save

\#### Bulk Editing

Use this when you need to modify the information for multiple items at once.

* Select the **CSV Download** button on the **Item Management** page
* Change the item information to be modified in the downloaded CSV file
* Upload the modified CSV file
* Review the modification results after upload is complete

\### ⚠️ Important Notes When Editing

* Changing information for items currently on sale may impact service operations.
* We recommend performing a **small-scale test edit** before bulk editing.
