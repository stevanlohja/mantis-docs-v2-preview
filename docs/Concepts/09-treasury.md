# Treasury

This page describes a proposal to establish a *treasury* associated with the Ethereum Classic blockchain. 

## Context

At IOHK, we believe that community input is essential for delivering a robust Ethereum Classic roadmap and executing its plans by attracting talented DApp developers. Promoting greater engagement is crucial for establishing independence, and ultimately, this grants the ecosystem sustainability for *innovation, stability, and growth*.

Because the proposal introduces a change at the protocol level, the Proto-Treasury introduces simple on-chain governance and built-in obsolescence triggers for the community to assess its value directly.
In other words, if the proposal does not meet expectations, it stops operating.

## Motivation

The motivation for having a treasury in place is to establish a steady funding income to ensure a blockchain's sustainability. The network is continually under attack, as seen in the recent 51% attacks on the Ethereum Classic blockchain, and this requires constant innovation to guarantee the project's support and development.

> Note: 51% attacks occur when some miners (comprising more than 50% of the network's mining hash rate) collude to cause network disruption.

The IOHK team has proposed a solution to 51% attacks in [ECIP 1097](https://ecips.ethereumclassic.org/ECIPs/ecip-1097)). In future, as yet unknown attacks will require other innovations.

Therefore, establishing a treasury for funding purposes supports the substantial system maintenance required to implement the innovation and diversity that a robust network needs.

The Proto-Treasury will offer sustainable and consistent funding for the development and maintenance of the Ethereum Classic underlying blockchain.

## Solution

The proposed Proto-Treasury solution is straightforward in its optimization for speed of implementation. The treasury system also includes a specification and a Solidity smart contract in the [Github repository](https://github.com/input-output-hk/etc_treasury_system).

If the proposal is accepted, 80% of existing mining rewards will continue as rewards to miners, and 20% will go to the Proto-Treasury smart contract. This treasury will then be distributed as decided by the community.

Miners will be able to choose whether to send 20% to the Proto-Treasury or burn rewards through an op-out mechanism.

If the proposal is not accepted, and the Proto-Treasury smart contracts are not active, miners will recover access to full rewards by default.

### Distribution

Initially, the treasury funds will be distributed to three teams of client developers and the open community fund, where 30% will be allocated to each team and 10% - to the open community fund.

Through the on-chain smart contract governance, a super-majority vote of 60% will be enough to add or remove members from the smart contract as well as to close the whole treasury.

For further reading on the subject, please follow these links:

* [Proto Treasury ECIP-1098](https://ecips.ethereumclassic.org/ECIPs/ecip-1098)
* [ECIP-1098 Issues Discussion](https://github.com/ethereumclassic/ECIPs/issues/350)
* [Podcast describing the proposal with Brian Mckenna](https://www.youtube.com/watch?v=55Quk7MDvXA)
