metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/instant-item-purchase
---

# Buy Items Instantly

## Buy Items Instantly Feature

The Instant Item Purchase feature supports players by immediately providing the NEXT Market payment screen when essential consumable items run low during gameplay or when in-game item purchases are selected. This allows players to buy items and continue gameplay without interruption.

## Target Items and Provision Method by Environment

### Target Items

This feature is suitable for consumable items essential to game progression. 

* Example Applicable Items
  * Revival Tickets, EXP Recovery Tickets, Stamina Recovery Items, Retry Tickets, and other consumable items necessary to continue gameplay
* Beyond consumables, it can be applied to all items sold within the game.

### Provision Method by Environment

The Instant Item Purchase feature provides the payment screen differently depending on the game execution environment.

<table><thead><tr><th width="175.646728515625">Environment</th><th>Method</th></tr></thead><tbody><tr><td>PC Client</td><td>Provided as a payment window pop-up</td></tr><tr><td>Web-based Game</td><td>Provided as a page transition within a web browser</td></tr><tr><td>Mobile Native App</td><td>Not applicable</td></tr></tbody></table>## User Flow

### 1. Direct Item Purchase Flow

When the Direct Item Purchase feature is applied, payment proceeds via the following streamlined flow:

* Flow
  * Game Play &gt; Select Item &amp; Quantity &gt; Proceed to NEXT Market Payment Screen &gt; Complete Payment &gt; Return to Game
* Benefits
  * Minimizes user movement compared to existing flow
  * Reduces additional setup effort from an operational perspective (e.g., API configuration)

### 2. Existing Flow (Without Instant Item Purchase)

Without the Instant Item Purchase feature, NEXT Market can be used via the following flow.

<table><thead><tr><th width="193.2725830078125">Case</th><th>Flow</th></tr></thead><tbody><tr><td>Go to NEXT Market</td><td><ul><li>Game Play &gt; Go to NEXT Market &gt; Browse Item List &gt; Select Item &gt; Item Details Screen &gt; Select Purchase Item &amp; Quantity &gt; Proceed to Payment &gt; Return to NEXT Market after Payment Complete</li><li>Game Play &gt; Go to NEXT Market &gt; Browse Item List &gt; Select Item and Quantity to Purchase &gt; Proceed to Payment &gt; Return to NEXT Market after Payment Completion</li></ul></td></tr><tr><td>Navigate to Item Details Screen</td><td>Game Play &gt; Select Purchase Item &gt; NEXT Market Item Detail Screen &gt; Select Purchase Item and Quantity &gt; Proceed to Payment &gt; Return to NEXT Market After Payment Completion</td></tr></tbody></table>⚠️ Important Notes When Providing the Item Detail Screen Navigation Path

When calling the API to request a one-time token for store authentication, the redirectPath must be set to the format below to activate the item detail screen navigation function.

```
/shop/sales/{sale_id}
```

### 3. Direct Item Purchase vs. Existing Navigation Path Comparison

| Category        | Direct Item Purchase | Existing Path (Go to NEXT Market) | Existing Path (Go to Item Detail Screen) |
| --------- | ----------- | ---------------------- | -------------------- |
| Item Exploration Path | In-game         | NEXT Market            | In-game                  |
| User Navigation Steps | Minimized         | Multi-step                    | Multi-step                  |
| Payment Access     | Immediate          | Via item shop list          | Via item detail screen         |
| Potential Game Exit | Low          | Relatively high               | Relatively high             |
| Operational Setup Effort | Low          | Low                     | Requires setup per product listing     |

## How to Implement Direct Item Purchase

Implementation of the Direct Item Purchase feature is possible after prior consultation with LINE NEXT.
The specific implementation method will be determined through consultation based on the target items, game environment, and user flow structure.
