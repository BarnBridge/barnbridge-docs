# Overview

BarnBridge DAO is an initiative, which grants voting rights to the $BOND holders and lay the foundation for the SMART Yield and SMART Alpha products. The BarnBridge DAO is the only source of minting products on top of the Blockchain and launch them into the wild.

BarnBridge DAO empowers the community by enabling decentralized decision making on the BarnBridge protocol.

It is governed by the $BOND tokens and is the core component of the BarnBridge platform.

## Diamond Standard

BarnBridge is intent on leading the way in the adoption of new approaches, technologies, and standards that have been proven superior to the general way of doing things. Our BOND staking contract, called Barn, is built on the Diamond Standard.

The Diamond Standard is a modular approach to deploying smart contracts, that allows greater flexibility in developing and adding incremental upgrades. Nick Mudge, the standard creator, highlights a few main Diamond features:

1. **Your contract exceeds the 24KB maximum contract size.** You may have related functionality that it makes sense to keep in a single contract, or at a single contract address. A diamond does not have a max contract size.
2. **A diamond provides a way to organize contract code and data.** You may want to build a contract system with a lot of functionality. A diamond provides a systematic way to isolate different functionality and connect them together and share data between them as needed in a gas-efficient way.
3. **A diamond provides a way to upgrade functionality.** Upgradeable diamonds can be upgraded to add/replace/remove functionality. Because diamonds have no max contract size, there is no limit to the amount of functionality that can be added to diamonds over time. Diamonds can be upgradeable or immutable. It is also possible to make an upgradeable diamond and then at a later time remove its upgrade capability.

The Barn contract is complementary to the DAO and the DAO relies on it to read information about voting power. The DAO will have full control over the Diamond used by the Barn which means it can only be upgraded through the proposals accepted by the DAO.

## $BOND Total Supply

The $BOND token contract doesn't have the mint function, so the total supply is and always will be 10,000,000.

