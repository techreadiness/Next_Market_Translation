metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/c2c-preset-management
---

# C2C Preset Management

**The C2C Preset Management page is where you register and manage the categories (item classification hierarchy) used for C2C items.**\
After pre-registering the category information for C2C items, you can select and use the corresponding category when registering a C2C sale. \
Category settings are reflected in the Marketplace filter area, and items are displayed by category.

<figure><img src="../.gitbook/assets/프리셋.png" alt=""><figcaption></figcaption></figure>## Registering C2C Presets

C2C item category settings can be configured up to 2 levels deep.

* Level 1: Parent Preset
* Level 2: Child Preset

{% stepper %}
{% step %}
### Selecting the C2C Preset Management Page

* Access the NEXT Market Console
* Select the **C2C Preset Management** page from the left menu
{% endstep %}

{% step %}
### Select Preset Creation

* Select the Create Preset button to proceed to the registration screen.

<figure><img src="../.gitbook/assets/프리셋_등록.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter Basic Information

Enter the basic information for the preset (category).

| Field      | Value                                                                                                                                                                                                                                 |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Level         | <ul><li><p>Presets can be set to Levels 1 to 2</p><ul><li>Level 1 is the top-level category and cannot have parent presets</li><li>Level 2 is registered as a subcategory under Level 1</li></ul></li><li><p>Ex)</p><ul><li>Level 1: Weapons</li><li>Level 2: Bows, Greatswords, Staves, Crossbows, Daggers</li></ul></li></ul>                       |
| Parent Preset     | <ul><li><p>When registering a Level 2 preset, the parent preset (Level 1) must be set</p><ul><li>Level 1 presets cannot have a parent preset set</li></ul></li><li><p>Ex)</p><ul><li>Preset: Bow</li><li>Parent Preset: Weapon</li></ul></li></ul>                                                               |
| Color         | <ul><li>Set the color to be displayed in the category</li><li>Available colors: Blue, Yellow, Red, Green</li><li>No color applied when None is selected</li></ul><p>⚠️ We recommend registering color settings only in the Grade (Rarity) category.</p><ul><li><p>Ex) </p><ul><li>Legendary: Yellow</li><li>Rare: Blue</li><li>High: Green</li></ul></li></ul> |
| Preset Name (Multilingual) | <ul><li>Supports multilingual input: en, ko, ja, th, zh</li><li><p>Value displayed on the item detail screen in the Exchange</p><ul><li>Must be registered for languages provided by the marketplace</li></ul></li></ul>                                                                                                    |

<figure><img src="../.gitbook/assets/프리셋_기본정보.png" alt=""><figcaption></figcaption></figure>{% endstep %}

{% step %}
### Item Registration

Items (SKUs) to be included in the preset can be registered not during initial preset registration, but via the edit function after registration is complete.

<figure><img src="../.gitbook/assets/프리셋_아이템.png" alt=""><figcaption></figcaption></figure>{% endstep %}
{% endstepper %}

## C2C Preset Modification

**Information for already registered presets can be modified.**

* Access the **NEXT Market Console**
* Select the **C2C Preset Management** page from the left menu
* Choose the preset to edit from the preset list
* Click the **Edit** button
* Save after modifying the preset information

<figure><img src="../.gitbook/assets/프리셋_수정.png" alt=""><figcaption></figcaption></figure>### ⚠️  Important Notes When Editing

* Please register presets only after prior consultation with LINE NEXT.
* Preset level changes are not possible. If a level change is needed, a new preset must be registered.
* Changing information for presets already in operation may impact service operations.
