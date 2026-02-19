metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/next-market-console-user-guide/mission-management/mission-type-setup
---

# Mission Type Setup Guide

A mission&#x27;s operation method and reward distribution structure vary based on the mission type + round (episode) + achievement goal settings.
Please select the mission type that best suits your purpose by referring to the examples below.

## SINGLE - Single Goal Mission

* Rewards are distributed upon achieving the single goal.
* Depending on whether rounds are set, it can be operated as a one-time mission.

| Field | Value  | Example |
| ----- | ------ | ------- |
| Mission Type | SINGLE | SINGLE  |
| Rounds    | Not Set    | 1       |
| Achievement Goal | Number of Achievements  | 1       |

### Operation Method

* Completion occurs immediately upon goal achievement
* Cannot be repeated

## SINGLE - Repeat Goal Mission

* Used when you want to encourage the same action to be repeated per session.
* Operates as a repeat mission depending on the round setting.

| Field | Value   | Example |
| ----- | ------- | ------- |
| Mission Type | SINGLE  | SINGLE  |
| Rounds   | Set to 2 or more | 2       |
| Achievement Goal | Number of Achievements   | 1       |

### Operation Method

| Round | Goal | Achieved | Status |
| --- | -- | -- | -- |
| 1st Round | 1  | 1  | Complete |
| 2nd Round | 1  | 1  | Complete |

## ACCUMULATE - Cumulative Achievement Mission

* The target value is fixed, and the achievement count accumulates even when the round changes.
* Rewards are granted when the cumulative count reaches the target.

| Field | Value      | Example    |
| ----- | ---------- | ---------- |
| Mission Type | ACCUMULATE | ACCUMULATE |
| Rounds     | Set to 2 or more    | 3          |
| Achievement Goal | Cumulative Achievement Count   | 10         |

### How It Works

⚠️ **Achievement counts are NOT reset** when changing rounds.

| Round | Goal | Achieved | Status        |
| --- | -- | -- | --------- |
| Round 1 | 10 | 4  | 4/10, In Progress |
| Round 2 | 10 | 7  | 7/10, In Progress |
| Round 3 | 10 | 10 | 10/10, Complete |

## DIFFICULTY — Increasing Difficulty Mission

* The difficulty of the achievement goal increases with each round.
* If the number of rounds and the number of difficulty settings do not match, it resets to the initial difficulty.

⚠️ It is recommended to set the number of rounds and the number of difficulty settings to be the same.

| Field | Value      | Example    |
| ----- | ---------- | ---------- |
| Mission Type | DIFFICULTY | DIFFICULTY |
| Rounds     | Set to 2 or more    | 4          |
| Achievement Goals | Difficulty Level     | 20,40,60   |

### How It Works

| Round    | Goal                                                 | Achieved | Status         |
| --- | -------------------------------------------------- | -- | ---------- |
| 1st Round | 20                                                 | 10 | 10/20, In Progress |
| 2nd Round | 40                                                 | 5  | 5/40, In Progress  |
| 3rd Round | 60                                                 | 40 | 40/60, In Progress |
| 4th Round | <p>20<br>⚠️ If the number of rounds and difficulty settings don&#x27;t match, it resets to the initial difficulty</p> | 20 | 20/20, Complete  |

## CHALLENGE - Collection Mission

* This mission bundles multiple missions into a single set.
* All missions must be completed to receive rewards.

| Field | Value     | Example   |
| ----- | --------- | --------- |
| Mission Type | CHALLENGE | CHALLENGE |
| Rounds       | Not Set       | 1         |
| Achievement Goal | Related Mission ID  | 1,2,3     |

### How It Works

#### Example of Failure

| Rounds          | Goal         | Achieved | Status      |
| ------------ | ---------- | -- | ------- |
| Mission 1         | 1          | 1  | Complete      |
| Mission 2         | 1          | 1  | Complete      |
| Mission 3         | 1          | 0  | In Progress     |
| CHALLENGE Mission | Mission 1,2,3 Achieved | 0  | **In Progress** |

#### Achievement Example

| Round          | Goal         | Achieved | Status     |
| ------------ | ---------- | -- | ------ |
| Mission 1         | 1          | 1  | Complete     |
| Mission 2         | 1          | 1  | Complete     |
| Mission 3         | 1          | 1  | Complete     |
| CHALLENGE Mission | Mission 1,2,3 Achieved | 1  | **Complete** |

## ⚠️ Administrator Notes

* Mission types cannot be changed after registration.
* Ongoing missions cannot be modified.
* If round and goal settings do not match, unexpected behavior may occur.
