# Beginner's Guide to Governance

## Intro

“BarnBridge” does not refer to an incorporated entity based out of any legal jurisdiction. It is an open source suite of applications for managing risk within blockchain-based financial systems. Its founding team and the community that has emerged since its inception coordinate the continued development of this suite through a combination of formalized decision-making and informal channels for reaching consensus. 

Its formalized decision-making is conducted through a structure referred to as a “DAO”, or Decentralized Autonomous Organization. The DAO is architected as a series of smart contracts on the Ethereum blockchain that allow users to deposit BarnBridge’s governance token, BOND, to gain voting power. This voting power then allows users to decide on how to introduce new, or maintain existing, applications, as well as how to allocate collective resources in the shared treasury. With its DAO, BarnBridge becomes accessible to anyone with an internet connection and an Ethereum wallet.

The aforementioned informal channels refer to where the BarnBridge community congregates and discusses ideas, user feedback, and prospective DAO proposals. Such discussions happen primarily on our Discord server, with longer-form conversations being held on the BarnBridge forum. For our Mandarin-speaking users, we do also maintain a WeChat group with a designated community manager.

## The State of BarnBridge Governance Today

As mentioned above, BarnBridge governance relies heavily on informal consensus gathering to make decisions. This reflects the early nature of the project: a core team and some hundred engaged community members are able to have orderly discussions without issue. The following process flow reflects what a good-faith effort for participating in governance would look like.

1. **Establishing a Reputation:** Whether publicly or pseudonymously, you can establish yourself as an engaged member of the community by participating in conversations on our Discord and the BarnBridge forum. You can also submit questions to our biweekly community calls via Github. 
2. **Getting Feedback via Our** [**Intake Form**](https://docs.google.com/forms/d/e/1FAIpQLSftA8dem1TfkzT4rK71pHzTNXxYJwX-BMITLcOoP_WQF8fteQ/viewform)**:** The community has approved an Integration Team that works with community members and external parties to assess the feasibility of proposed ideas and see through the implementation of successful ones. Should you have an idea you would like to push forward, you can confer with the Integration Team to first brainstorm the idea. 
3. **Notify with a** [**Forum Post**](https://forum.barnbridge.com/)**:** Once you have workshopped your idea with the Integration Team and, ideally, other community members in the Discord, you can then make a comprehensive forum post outlining it. This will allow you to gain formalized feedback from the community and core team members, as well as make it easier for the discussion to be shared via the BarnBurner newsletter or on Twitter.
4. **Wait 2 Days and Submit a 5-Day** [**Snapshot Vote**](https://signal.barnbridge.com/#/)**:** After your forum post has been up for 48 hours, you should feel free to propose a Snapshot vote on the idea. **This is the most subjective part of the process.** You should make a clear effort to incorporate the feedback you received in the forum discussion into the Snapshot proposal. Previously successful Snapshot votes have set a precedent for what sufficient approval looks like \(&gt;90% approval, &gt;50 addresses participating, &gt;60,000 BOND participation, all sans the core team\) but these are moving goal posts that will change as more BOND come into circulation and more members join the community. 
5. **Proposal Included in the Next DAO Vote:** If you Snapshot concludes with clearly unanimous agreement among the community’s most engaged members, it will be included in the next on-chain DAO vote. These votes will occur periodically as the core team continues to work through its roadmap. If your Snapshot vote did not garner significant turnout or unanimous approval, feel free to try it again with the new feedback you receive.

The current state of governance reflects **a\)** the gas costs associated with holding DAO votes on-chain, and **b\)** the small community size of BarnBridge. As BarnBridge grows, we will look to build out a more robust governance structure that will allow for the core team to merge with the community via a council entity, and for there to be specialized working groups through which specific topics can be routed. 

## On-Chain Voting

Currently, the core team coordinates when DAO votes occur in order to optimize for this gas intensity. DAO votes are reserved for actual on-chain actions, whether that be deploying smart contracts or allocating treasury funds. This means that such votes will occur periodically as roadmap items get deployed \(e.g., new applications, new liquidity mining reward pools\) on-chain; such votes could however be called by any community member willing to pay the associated gas fees. Each DAO vote can support up to 10 separate on-chain actions, which is why we currently roll successful Snapshot proposals into them. 

It is important to note how voting power is determined in such votes. For a participant’s BOND holdings to count for their vote, the tokens must be staked in the DAO. 

[How to stake in the DAO?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-obtain-voting-power-on-the-dao)

The participant can then choose to either leave their BOND unlocked, or leave it locked for up to a year. One unlocked BOND gives the user one vBOND voting share; locking up one BOND for a whole year gives the user 2 vBOND voting shares. This bonus decays linearly relative to the remaining duration of the lock. If you lock for one year, after 6 months only 50% of the bonus will remain; after 9 months, only 25%; and after a year, your BOND staked and vBOND will be identical.

[How to lock BOND to increase voting power?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-lock-bond-to-increase-voting-power)

Worth noting: users can opt to delegate their vBOND to another user. This allows smaller users, who may be put off by the cost of gas fees associated with casting a vote, to ensure that an aligned representative can vote on their behalf. 

* [How to delegate voting power \(vBOND\)?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-delegate-voting-power)
* [How to return delegated voting power \(vBOND\)?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-return-delegated-voting-power)

### Thresholds

To be proposed and passed, a DAO vote must meet the following thresholds:

* **Proposer’s vBOND needs to be &gt;= 1% of Total BOND Staked:** To submit a proposal for vote, the address doing so must have vBOND greater than 1% of the total BOND staked. For example, if there are 1000 BOND staked, a user will need either 10 unlocked BOND staked, or 5 BOND locked for a year. 
* **Minimum 40% of Staked BOND Must Vote:** For a vote to be considered legitimate, the amount of vBOND that participates in the vote must be &gt;= 40% of the total BOND staked. For example, if there are 1000 BOND staked, the participation of 400 vBOND would be enough to achieve quorum. 
* **Minimum 60% of Participating vBOND Must Approve:** A DAO vote is considered approved if the vBOND quorum is reached and 60% of it votes in the affirmative once the vote concludes.  
* [How to create a proposal?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-create-a-proposal)
* [How to vote on the proposal?](https://docs.barnbridge.com/how-to-guides/barnbridge-dao/how-to-vote-on-the-proposal)

### Process Flow

Each proposal is formed of:

* ID
* Title
* Description
* List of targets \(addresses\)
* List of values
* List of signatures
* List of calldata

A proposal can execute up to 10 different actions, but they must be done so atomically \(i.e., all or nothing\).

In order to give DAO participants enough time to stake, vote, check and discuss proposals, each of the following periods lasts for 4 days: Warm-up, Voting, Queued for execution, Grace.

![](https://lh3.googleusercontent.com/VcxgxKHBcm_Dr6pS6z50X5fUx1_utFgQbuB1ygXeU4fLp4MhW6CRAd4pgJ9RtuKw_3xFeeEHjxSLh-BhROhDBy5wKhRSShNjVyKazttK1WYPNR2Gv5wlG-pGk2kFUKCIEzhzux3_)

Notice, the **Queued** period is the only state that requires a user action to activate. So when it is activated, its 4-day lasting period counts from the moment when the voting ended, not when the user did the action. For example, if voting ends and someone queues the proposal 2 days after, it will not stay in the queue for 4 more days but only 2 days because 2 have already passed.

During the **Queued** period, a special type of proposal, referred to as an Abrogation Proposal, can be added to the original proposal. While such a proposal allows for a last-minute action to be added, it requires 50% of staked BOND to participate; essentially, it serves to provide extra bandwidth for DAO action in the case of an emergency vote.

Once a proposal is accepted, it will have to wait in a queue before it can be executed. During this time, it can be canceled by:

* the creator;
* anyone if the creator’s balance falls below the 1% threshold;
* cancellation proposal.

Once a proposal becomes executable, any users can call the execute function. If the proposal is not executed during the **Grace** period, it is marked as expired and cannot be executed anymore.

Feel free to [jump in our Discord](https://discord.gg/DcUJvqnT), [submit a forum post](https://forum.barnbridge.com/), or [add a Snapshot vote](https://signal.barnbridge.com/#/).

