---
description: >-
  Overview of how SMART Alpha works and what users can expect in different
  scenarios
---

# Beginner's Guide to SMART Alpha

**SMART Alpha** allows users to calibrate their exposure to the performance of an underlying asset. It does so by redistributing the performance of an aggregated pool of the underlying asset between two groups of users: a senior side, and a junior side. Whereas the senior side of the pool receives dampened exposure to both upside and downside movements, the junior side takes on levered exposure. Put another way, junior depositors are buying asset price risk off of senior depositors, guaranteeing them price protection up to a certain threshold, in exchange for greater upside potential. 

The outcome is a two-sided marketplace for asset price risk, generalizable to any ERC-20 token.

## How to Enter or Exit a SMART Alpha Pool

SMART Alpha implements an epoch-based approach in which users can only enter and exit pools **once a week at Monday, 9:30 AM EST / EDT**. In between epochs, users will be able to signal their intent to enter, exit, or switch sides within the pool for their given ERC-20 token. The composition of these pools, namely, the ratio of deposits in the senior side versus those in the junior side, are what determine how much downside protection the former, and for the latter, leverage, receives.

Depositors on both sides of a given pool receive an ERC-20 token as proof of liquidity. For example, if you were to deposit Ether into its senior SMART Alpha pool, you would receive a bb_senETH token in return. Like any ERC-20, these tokens would then be further usable within other trading, lending, or derivative applications. These ERC-20 tokens are perpetual, meaning that new epochs do not bring new tokens. 

{% hint style="info" %}
Both entering and exiting SMART Alpha pools requires the user to deposit either the underlying or derivative asset, respectively, prior to the advancement of the next epoch. This could be done six days and 23 hours in advance, or a minute in advance.
{% endhint %}

## How Junior and Senior Outcomes are Calculated

The current implementation of SMART Alpha calculates senior rates as a function of junior-side pool dominance. Senior rate is defined as the maximum amount of downside price movement the underlying asset can experience in a week before senior depositors suffer dollar-denominated losses. Junior dominance is defined as the share of a given ERC-20 token’s pool that is comprised of junior depositors.

**There are two things to note under the current model:**

* **The senior rate is calculated as 80% of junior pool dominance**
* **The senior rate is capped at 35% downside protection for any given epoch**

Consider the following illustrative examples:

### **At 50% Junior Dominance**

![At +10% price action, the senior side forgoes 82.37% of its relative upside.](<.gitbook/assets/image (21).png>)

![At -10% price action, the senior side is compensated for nominal loss until the 35% threshold is met](<.gitbook/assets/image (22).png>)

![At -50% price action, the senior side begins to take losses after the 35% thresholdd](<.gitbook/assets/image (23).png>)

### At 10% Junior Dominance

![At +10% price action, junior levered upside converges on 9.39x the underlying.](<.gitbook/assets/image (24).png>)

![At -5% price action, junior levered downside converges on 10x the underlying. ](<.gitbook/assets/image (25).png>)

![At -10% price action, the senior side is exposed to more nominal downside. ](<.gitbook/assets/image (26).png>)

### At 90% Junior Dominance

![At +10% price action, senior upside exposure converges on 55%.](<.gitbook/assets/image (27).png>)

![At -10% price action, the junior downside converges on 1x.](<.gitbook/assets/image (28).png>)

![At -50% price action, senior downside protection remains capped at 35%.](<.gitbook/assets/image (29).png>)

## SMART Alpha System Parameters

Once the smart contracts for SMART Alpha are deployed on a given blockchain network, there are only a handful of parameters that can be altered, the power with which to do so having been handed over to the BarnBridge DAO. These parameters are:

* Status of the Guardian Contract 
* Owner of the Guardian Contract
* Fee Structure
* Underlying Asset Price Oracle
* Accounting Model
* Senior Rate Model

Note that the Guardian Contract only holds the borrow to stop and resume deposits into SMART Alpha; it cannot exercise any control over deposited assets. 

{% hint style="info" %}
SMART Alpha only charges a fee on the winning side of a given epoch.
{% endhint %}
