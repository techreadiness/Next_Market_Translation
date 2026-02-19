metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/c2c-item-ability-management
---

# C2C Item Ability Management

**The Item Ability Management page is where you register and manage &#x27;ability items (types)&#x27; to be used for C2C items.**\
After pre-registering standard information such as ability names and display units, you can select and use these abilities when registering items or C2C sales.

Provided Features

* [Register Item Ability Settings](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#post-api-v1-item-ability)
* [Modify Item Ability Settings](https://next-market-admin.gitbook.io/next-market-docs/api/undefined-2#put-api-v1-item-ability-code)

## C2C Item Capability Registration (Individual Registration)

C2C item capability registration supports **individual registration**.
When registering a small number of item capabilities, you can create them through individual registration.

{% stepper %}
{% step %}
### Select the C2C Item Capability Management Page

* Access NEXT Market Console
* Select the **C2C Item Ability Management** page from the left menu
{% endstep %}

{% step %}
### Select Ability Registration

* Select the Ability Registration button to proceed to the item ability registration screen.

<figure><img src="../.gitbook/assets/아이템 능력 관리_등록.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter Basic Information

Enter the basic information for the item ability.

| Field | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ----- | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ability Code | <ul><li><p>Code for identifying and managing item abilities</p><ul><li>Item Ability: Attributes and stats possessed by an item</li></ul></li><li>Format: Character limit of 3 to 36 characters; must be a value users can infer; may use letters, numbers, and special characters</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Ability Name | <ul><li>Supports multilingual input: en, ko, ja, th, zh</li><li><p>Value displayed on the item detail screen within the Exchange</p><ul><li>Must be registered for languages provided by the marketplace</li></ul></li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Option Type | <ul><li>Defines the nature of the ability value</li><li><p>Option Type</p><ul><li>Base Stats (<code>BASIC</code>)</li><li>Enhanced Stat (<code>ENHANCE</code>): Ability altered through enhancement</li><li>Additional Stats (<code>ADDITIONAL</code>): Stats altered through enchanting or socketing</li><li>Refining Stats (<code>SMELTING</code>): Stats altered through refining or attribute application</li><li>Restriction Options (<code>CONSTRAINT</code>): Constraints added or modified by alterations</li><li>Item Quantity (<code>AMOUNT</code>): Value representing the quantity embedded within the item</li></ul></li><li>Item Ability Setting Registration API <code>keys.optionType</code> Passed as a value</li></ul><p>⚠️ Important Note</p><ul><li><strong>For base attributes that do not vary per item, it is recommended to register them together with the SKU during registration</strong> on the Item Management page<strong>.</strong></li><li><strong>The C2C Item Capability Management page is for registering capability items whose values may change during transactions</strong> for each item<strong>.</strong></li><li><strong>Please ensure the same ability is not registered</strong> in both menus<strong>.</strong></li></ul> |
| Display Format | <ul><li>Set <strong>how</strong> attribute values <strong>are displayed to users</strong></li><li><p>Display Format Selection</p><ul><li>Numeric Value (<code>NONE</code>): Display the input value as-is</li><li>100% (<code>PPERCENTAGE</code>)</li><li>+100 (<code>NUMERIC</code>)</li><li>100Lv (<code>LEVEL</code>)</li></ul></li><li>Item Ability Setting Registration API <code>keys.unitType</code> |</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Color    | <ul><li>Set the color to display the ability value</li><li><p>Available colors</p><ul><li><p>Yellow, Green, Blue, Magenta, Orange, Red, Gray, No Color</p><ul><li>No color will display the default color</li></ul></li></ul></li><li>Item Ability Setting Registration API <code>keys.color</code> Pass as a value</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

<figure><img src="../.gitbook/assets/아이템 능력 관리_기본정보.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## C2C Item Ability Registration (Bulk Registration)

**When you need to register multiple item abilities at once**, you can register them in bulk via CSV file upload.

{% stepper %}
{% step %}
### Select the C2C Item Ability Management Page

* Access the NEXT Market Console
* Select the C2C **Item Capability Management** page from the left menu
{% endstep %}

{% step %}
### Download the Template

* Select the **Download Template** button to download the **CSV template file** for bulk item capability registration.
* The template includes the basic columns required for registering item capabilities.

<figure><img src="../.gitbook/assets/아이템 능력 관리_템플릿.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Create the Item Ability List

* Enter the information for the item abilities you wish to register into the downloaded **CSV template file**.
* Refer to the **Item Ability Registration (Individual Registration)** guide for how to fill out each field.

⚠️ Uploads may fail if required fields are missing or the format is incorrect.

<figure><img src="../.gitbook/assets/아이템 능력 관리_템플릿 엑셀.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Uploading the CSV

* Select and upload the completed CSV file.
* After selecting the file, click the **Upload** button to proceed with bulk item ability registration.

#### ⚠️ Important Notes for Bulk Registration

* CSV upload is used for **registering new item abilities or modifying existing registered information**.
* We recommend performing a **small-scale test upload** before registering via CSV upload.

<figure><img src="../.gitbook/assets/아이템 능력 관리_CSV 업로드.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## C2C Item Ability Modification

**If you need to change information for an already registered ability,** you can modify it using either **individual modification** or **bulk modification** methods.

### C2C Item Ability Modification Methods

#### Individual Modification

Use this when modifying the information for an individual item ability.

* Access **NEXT Market Console**
* Select the **C2C Item Capability Management** page from the left menu
* Select the capability to modify from the item capability list
* Click the **Edit** button
* Save after changing the item information

<figure><img src="../.gitbook/assets/아이템 능력 관리_수정.png" alt=""><figcaption></figcaption></figure>#### Bulk Editing

Use this when you need to modify the information for multiple item abilities at once.

* Select the **CSV Download** button on the **C2C Item Ability Management** page
* Change the item ability information to be modified in the downloaded CSV file
* Upload the modified CSV file
* Verify the modification results after upload completion

<figure><img src="../.gitbook/assets/C2C 아이템 능력 관리_업로드.png" alt=""><figcaption></figcaption></figure>### ⚠️  Important Notes When Editing

* Please register item abilities only after prior consultation with LINE NEXT.
* Changing information for items currently on sale may impact service operations.
* We recommend performing a **small-scale test edit** before bulk editing.
