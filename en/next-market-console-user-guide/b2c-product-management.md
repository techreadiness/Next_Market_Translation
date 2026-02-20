# b2c-product-management

### metaLinks: alternates: - >- https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/b2c-product-management

## B2C Product Management

The B2C Product Management page allows you to register and manage B2C products.

This page provides B2C product-related API functions within the Console environment.

* Provided Functions
  * [섹션 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#post-api-v1-sale-b2c-section)
  * [섹션 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-3#patch-api-v1-sale-b2c-section-sectionid)
  * [판매 등록](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#post-api-v1-sale-b2c)
  * [판매 변경](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-4#patch-api-v1-sale-b2c-b2csaleid) ⚠️ Important Notes
* B2C product registration does not support CSV upload. All B2C products must be registered individually via the Console.
* Please consult with LINE NEXT beforehand before registering B2C products.

### Section Management

Sections are **classification areas for displaying B2C products in groups**. You can use sections when you have multiple product types or need to distinguish between items.

#### Section Configuration Policy

* Number of sections that can be displayed: **Minimum 2 \~ Maximum 4**
* To ensure stable UI, the **maximum is limited to 4**.
* If section configuration is not required, **you do not need to register any sections.**

{% stepper %}
{% step %}
#### Selecting the B2C Product Management Page

* Access the NEXT Market Console
* Select the **B2C Product Management** page from the left menu
{% endstep %}

{% step %}
#### Registering a Section

* Select the Add Section button in the Section Management area.
* Proceed to the section registration screen.
{% endstep %}

{% step %}
#### Enter Section Information

| Field         | Value                                                                                                                                                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Section Name  | <ul><li>Multilingual Input Support: en, ko, ja, th, zh</li><li>Value displayed as the section title on the item shop page</li><li>Must be registered for languages provided by the marketplace</li></ul>                                                                                                                                                             |
| Icon Image    | <ul><li><p>Upload Method</p><ul><li>URL input: Enter the URL of an already uploaded media file</li><li>File Upload: Select and upload a local file</li></ul></li><li><p>Supported formats</p><ul><li>IMAGE: JPG, PNG, WebP</li></ul></li><li><p>Upload Limit</p><ul><li>File size: 10MB or less</li><li>Image Size: 72x72px including background</li></ul></li></ul> |
| Display Order | <ul><li>Can be set within the range 1 to 4</li><li>Sections are displayed according to the set order</li></ul>                                                                                                                                                                                                                                                       |
| Activation    | <ul><li>Controls whether the section is displayed</li><li>Deactivated sections are not displayed on NEXT Market</li></ul>                                                                                                                                                                                                                                            |
{% endstep %}

{% step %}
#### Section Editing

* Registered section information can be modified.

⚠️ Important Notes

* Section edits are **immediately reflected on NEXT Market**.
* Changing the display order or section name may affect the actual product display screen. **Please exercise caution when making changes during operation**.
{% endstep %}
{% endstepper %}

### B2C Product Registration

B2C product registration allows you to create B2C products and manage sales information. Products are configured by entering basic information, price, purchase restrictions, sales period, and linked item details.

{% stepper %}
{% step %}
#### Select the B2C Product Management Page

* Access the NEXT Market Console
* Select the **B2C Product Management** page from the left menu
{% endstep %}

{% step %}
#### Product Registration

* Select the Product Registration button to proceed to the product registration screen.
{% endstep %}

{% step %}
#### Enter Basic Information

Enter the basic information for the B2C product.

| Field               | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Media               | <ul><li><p>Upload Method</p><ul><li>URL Input: Enter the URL of an already uploaded media file</li><li>File Upload: Select and upload a local file</li></ul></li><li><p>Supported Formats</p><ul><li>IMAGE: JPG, PNG, WebP</li></ul></li><li><p>Upload Limit</p><ul><li>File size: 10MB or less</li><li>Image Size: 514x514px including background</li></ul></li></ul>                                                                                                                                                                                                                                                                             |
| Media Type          | <ul><li>Currently only image types can be selected</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Product Name        | <ul><li>Multilingual input support: en, ko, ja, th, zh</li><li>Value displayed as the product title on the item shop page</li><li>Must be registered for languages provided by the marketplace</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Product Description | <ul><li>Supports multilingual input: en, ko, ja, th, zh</li><li>Value displayed as the product description on the item shop page</li><li>Must be registered for languages provided by the marketplace</li><li><p>Product Description Writing Guide</p><ul><li><p>Required Content</p><ul><li>Item description applicable to the product</li><li>Refund policy</li><li>Item delivery method (e.g., mailbox delivery, etc.)</li></ul></li><li><p>Optional Content</p><ul><li>Item restrictions applicable to the product (e.g., character binding)</li><li>Purchase Restriction Conditions (e.g., 2 purchases per day)</li></ul></li></ul></li></ul> |
{% endstep %}

{% step %}
#### Price Information Input

Set the price for B2C products.

⚠️ B2C prices cannot be modified after registration. As this is a critical operational value, please set it carefully during registration.

\| Field | Value | | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| Free Product |

* Check if the product is free
* Free products do not require price information

\| | Refund Type |

* Select according to the game's refund policy
  * Non-refundable
  * Refundable
  * Partial Refund

\| | Product Price (Fiat) |

* Enter the amount in supported currencies: USD, KRW, JPY, TWD, THB, IDR, PHP
* Format: Enter up to two decimal places
* However, price must be within the minimum to maximum range of the supported currency
  * USD: 1 \~ 750,000
  * KRW: 500 \~ 2,000,000
  * JPY: 100 \~ 110,000,000
  * TWD: 30 \~ 999,999
  * THB: 1 \~ 3,000,000
  * IDR: 1,000 \~ 5,000,000
  * PHP: 6 \~ 100,000

\| | Product Price (USDt) |

* Enter USDt amount
* Format: Input possible to two decimal places
* However, prices must be entered within the minimum to maximum range
  * USDt: 0.1 \~ 750,000

|
{% endstep %}

{% step %}
#### Purchase Restrictions and Settings Input

Enter settings related to the purchase and display of B2C products. This determines how B2C products are displayed and purchased within the Market UI.

\| Field | Value | | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| Display Section |

* B2C products are displayed in the selected section from registered sections

\| | Total Purchase Limit |

* Enter the total quantity purchasable per account
* Setting to 0 allows unlimited purchases

\| | Maximum Purchase Quantity per Order |

* Enter the maximum quantity purchasable per order
* Maximum of 100 items

\| | Shipping Type |

*   Select the shipping method to be used for the purchase

    * Automatic Shipping: System automatically ships upon purchase completion
    * Manual Shipping: Ship manually at a specific time after purchase completion

    ⚠️ Manual shipping requires prior consultation with LINE NEXT

\| | Display Order |

* Enter the display order of products within the section

\| | Adult Verification Required |

* Enable if the product requires adult verification
* Product images will not be displayed until adult verification is completed; images will display normally after verification
* Example image (before adult verification)

\| | Periodic Sales Type |

* Set whether to periodically reset the purchase quantity limit per account
  * None: No reset
  * Daily (`DAILY`): Reset daily
  * Weekly (`WEEKLY`): Reset weekly
  * Monthly (`MONTHLY`): Reset monthly
* The value passed to the Sales Registration API `abilties.periodicType` Passed as a value

\| | Reset Basis Date |

* Enter the reference time when reset will be applied for periodic sales settings
* Enter in yyyy-MM-dd HH:mm format
* Example Settings
  * Registered as a past point relative to the opening date
    * None: No setting required
    * Opening date: 2025-12-16 10:00 KST (Tuesday)
    * Daily: 2025-12-15 10:00 KST = Reset daily at 10:00
    * Weekly: 2025-12-09 10:00 KST = Reset weekly at 10:00 KST on Tuesdays
    * Monthly: 2025-12-01 10:00 KST = Resets at 10:00 AM on the 1st of each month

|
{% endstep %}

{% step %}
#### Enter Sales Period

Set the start and end dates for B2C product sales. Products will only be displayed on the item shop page during the set period.

| Field            | Value                                                                                         |
| ---------------- | --------------------------------------------------------------------------------------------- |
| Sales Start Date | <ul><li>Set the start time for B2C products</li><li>Format: yyyy-MM-dd HH:mm (KST)</li></ul>  |
| Sale End Date    | <ul><li>Set the end date for the B2C product</li><li>Format: yyyy-MM-dd HH:mm (KST)</li></ul> |
{% endstep %}

{% step %}
#### Enter List of Linked Items

* Enter the SKU and quantity of items to sell under this B2C product.

**Package Product Information**

* When selling a package product, you only need to register one SKU for the package item.
* Sub-items included in the package item will automatically display on the product detail page.

⚠️ The linked item list (SKUs) cannot be modified after registration. To change linked items, you must end sales for the registered product and register it anew.
{% endstep %}
{% endstepper %}

### Editing B2C Products

Editing B2C products is a feature used **when you need to change information for an already registered product**.

* Access **NEXT Market Console**
* Select the **B2C Product Management** page from the left menu
* Choose the product to edit from the product information list
* Click the **Edit** button
* Save after modifying the product information

\### ⚠️ Important Notes When Editing

* Changing information for products currently on sale may impact service operations. We recommend thorough review before making changes.
* Price information and linked item lists (SKUs) are non-editable fields.
  * If modification is necessary, please end sales of the existing product and re-register it as a new product.
* For products currently on sale or already sold out, key fields that could affect purchase history cannot be modified.
  * Fields that cannot be changed:
    * Sales start date
    * Total purchase limit quantity
