# Checkpointing

The purpose of the checkpointing system is to provide the Ethereum Classic blockchain with 51% attack resistance, giving protection to the chain and confidence to its users that the system is secure.  
> Note: 51% attacks occur when some miners (comprising more than 50% of the network's mining hash rate) collude to cause network disruption.

## Motivation

Proof-of-work blockchains need high amounts of hash power (mining participation) to secure a network. Ethereum Classic has undergone several 51% attacks in the past due to low mining participation.  
Checkpointing defends against these attacks by using a checkpointing federation of nodes to guarantee the blockchain's integrity. The checkpointing federation is a set of external trusted participants that provides independent verification of a group of blocks.
This solution is a temporary measure with a time horizon of 4-5 years. As soon as there are enough network participants and enough hash power to make an attack economically infeasible, checkpointing could be deactivated if the community agrees to it.

## Solution

The checkpointing nodes may be a new group structure (as a "federation of nodes" either from a standing committee or the result of a periodic election process) or based on a randomized selection from miners.  
Checkpoints are stored on a separate network, the proposed OBFT-based side chain.  
The blockchain's headers contain an additional value indicating a checkpointed position. The checkpointing federation validates this checkpoint position. The checkpoint indicates that the chain has been proven correct up to that point.

As a user, you know that a transaction is safe if it is in the checkpointed block or one of its ancestors.

The underlying technology used to coordinate the issuing of checkpoints is a variant of the Byzantine fault tolerant consensus protocol, the [Ouroboros BFT](https://eprint.iacr.org/2018/1049.pdf).


For more details, please read the [Ethereum Classic Improvement Proposals (ECIPs](https://github.com/ethereumclassic/ECIPs/blob/master/_specs/ecip-1097.md)), and [white paper](https://dimkarakostas.com/checkpointed_blockchains.pdf).
