# Senior Tranches \(Bonds\)

## Senior bonds

Senior tranches are represented by ERC-721 non-fungible tokens \(sBONDs\) that have a guaranteed yield for the life of the bond. Senior tranches have fixed APY and are less risky compared to junior tranches. 

The set of features that a senior bond has is:

* principal - the amount deposited in the bond;
* gain - the amount of token that will be gained \(this is used to determine the APY\);
* issuedAt - the issuance date;
* maturesAt - the maturity date; 
* liquidated - a flag used to determine if the senior bond was redeemed or not.

## Senior bonds APY

Senior APY determines the annual percentage for senior bonds at the current time. 

It can be derived for any and all senior bonds in existence by annualizing the percentage difference between the deposited value and the gained value using the following formula:

```text
((gain/principal) / (maturesAt - issuedAt)) * 365 * 100
```

![](../.gitbook/assets/apy_sen.png)

## ABOND

In order to provide the best UX for Juniors and encourage them to participate in our SMART Yield pools, we want the system to allow them to join the pool at any time. Moreover we want the possibility of instant withdrawal of at least part of their funds, without affecting the integrity of the system and keeping the guarantees.

To do that, we have to be able to calculate the profits and losses of the pool very efficiently. We do that by averaging all existing senior bonds into one "weighted average" ABOND with the following properties:

* Principal locked \(sum\) -&gt; ABOND.principal
* Guaranteed rewards \(sum\) -&gt; ABOND.gain
* Start timestamp -&gt; ABOND.issuedAt
* Weighted average end timestamp -&gt; ABOND.maturesAt

The aggregate sBOND \(ABOND\) represents the current Senior pool and it will help us calculate the health of the Senior pool at an instant. If the rewards generated by the Senior pool so far exceed the guaranteed rewards at this time \(abond.paid\), the extra reward can be considered profit for the junior pool \(and loss if it's negative\).

 ABOND parameters are recalculated each time new Senior bonds are purchased.

## Useful links

* [How to buy senior bonds?](../how-to-guides/smart-yield/how-to-buy-senior-bonds.md)
* [How to redeem senior bonds?](../how-to-guides/smart-yield/how-to-redeem-senior-bonds.md)
* [How to sell senior bonds?](../how-to-guides/smart-yield/how-to-sell-senior-bonds.md)

