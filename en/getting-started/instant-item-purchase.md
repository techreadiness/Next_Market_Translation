---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/instant-item-purchase
---

# Instant Item Purchase

## Instant Item Purchase Feature

The Instant Item Purchase feature provides immediate access to the NEXT Market payment screen when essential consumable items run low during gameplay or when players choose to purchase items within the game. This allows players to buy items and continue gameplay without interruption.

## Applicable Items and Provision Methods by Environment

### Target Items

This feature is suitable for consumable items essential to game progression.

* Example Applicable Items
  * Revival Tickets, EXP Recovery Tickets, Stamina Recovery Items, Retry Tickets, and other consumable items necessary to continue gameplay
* Beyond consumables, it can be applied to all items sold within the game.

### Delivery Method by Environment

The Item Direct Purchase feature provides different payment screen delivery methods depending on the game execution environment.

<table><thead><tr><th width="175.646728515625">Environment</th><th>Method</th></tr></thead><tbody><tr><td>PC Client</td><td>Provided as a payment window pop-up</td></tr><tr><td>Web-based Game</td><td>Provided as a page transition within a web browser</td></tr><tr><td>Mobile Native App</td><td>Not applicable</td></tr></tbody></table>

\## User Flow

### 1. Direct Item Purchase Flow

When the Direct Item Purchase feature is applied, payment proceeds via the following streamlined flow:

* Flow
  * Game Play > Select Item & Quantity > Proceed to NEXT Market Payment Screen > Complete Payment > Return to Game
* Benefits
  * Minimizes user movement compared to existing flow
  * Reduces additional setup effort from an operational perspective (e.g., API configuration)

### 2. Existing Flow (When Instant Item Purchase is Not Applied)

When the Instant Item Purchase feature is not applied, NEXT Market can be used with the following flow.

<table><thead><tr><th width="193.2725830078125">Case</th><th>Flow</th></tr></thead><tbody><tr><td>Go to NEXT Market</td><td><ul><li>Game Play > Go to NEXT Market > Browse Item List > Select Item > Item Details Screen > Select Purchase Item and Quantity > Proceed to Payment > Return to NEXT Market after Payment Completion</li><li>Game Play > Go to NEXT Market > Browse Item List > Select Item and Quantity to Purchase > Proceed to Payment > Return to NEXT Market after Payment Completion</li></ul></td></tr><tr><td>Navigate to Item Details Screen</td><td>Game Play > Select Purchase Item > NEXT Market Item Details Screen > Select Purchase Item and Quantity > Proceed to Payment > Return to NEXT Market After Payment Completion</td></tr></tbody></table>

⚠️ Important Notes When Providing the Item Detail Screen Navigation Path

When calling the API to request a one-time token for store authentication, the redirectPath must be set to the format below for the item detail screen navigation feature to activate.

```
/shop/sales/{sale_id}
```

### 3. Direct Item Purchase vs. Existing Navigation Path Comparison

| Category                 | Direct Item Purchase | Existing Path (Go to NEXT Market) | Existing Path (Go to Item Detail Screen) |
| ------------------------ | -------------------- | --------------------------------- | ---------------------------------------- |
| Item Exploration Path    | In-game              | NEXT Market                       | In-game                                  |
| User Navigation Steps    | Minimized            | Multi-step                        | Multi-step                               |
| Payment Access           | Immediate            | Via item shop list                | Via item detail screen                   |
| Potential Game Exit      | Low                  | Relatively high                   | Relatively high                          |
| Operational Setup Effort | Low                  | Low                               | Requires setup per product listing       |

## How to Implement Instant Item Purchase

If you wish to implement the Instant Item Purchase feature, it can be applied after prior consultation with LINE NEXT. The specific implementation method will be determined through consultation based on the target items, game environment, and user flow structure.
