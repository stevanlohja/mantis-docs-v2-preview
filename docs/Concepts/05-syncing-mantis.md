# Syncing Mantis

## Syncing
Mantis must be fully synchronized to be useful, which applies to both the wallet and the client. So, each node has to download blockchain data from other nodes using a peer-to-peer mechanism, and then the node must verify the data on the chain.  
Once the synchronization process is complete, the node is part of the network and can be interacted with through API.

Mantis supports `fast sync and `pruning` which help synchronize the data faster and reduce disk space on your node.

The syncing process operates on the blockchain, and data is stored in a [rocksdb database](https://rocksdb.org/).

## Syncing Process
The following is a brief description of the syncing process:
* Discovery: The process starts by checking pre-defined bootstrap node addresses for nodes that are always connected. Mantis then tries to find and build a list of peers (other nodes and clients already connected to the network).  
* [RPLx Connections](https://github.com/ethereum/devp2p/blob/master/rlpx.md) are made to these peers using the `max peers` option.  
* Some blacklisting is done on nodes that aren't ideal candidates for synchronization.
* Download: There are two primary states while syncing; an initial syncing for downloading and verifying all the existing blockchain data and ongoing syncing while on top of the chain.  
* In its initial state, Mantis downloads chain data from other clients.
* Verification: As Mantis downloads each block header and body, these blocks are verified by replaying the transactions in them.
* The client reaches full synchronization when it downloads the highest block. The highest block is the one that the community agrees is the top of the chain.
* Mantis then continues to fetch and sync new blocks produced since the initial sync.

To read more about the synchronization process in Ethereum, [refer to the Ethereum documentation](https://github.com/ethereum/devp2p/blob/master/caps/eth.md).

## Fast sync   
Fast sync is a technique used to speed up the initial synchronization of the local node with the Ethereum Classic blockchain.  
First, a pivot block is selected. The pivot block is a block number near the top of the chain, old enough to be safe from [chain reorganizations](https://blog.ethereum.org/2015/08/08/chain-reorganisation-depth-expectations/).   
Fast sync will download only the headers of blocks from the first (genesis) block to the pivot block, then switch to normal full sync, where each block is downloaded and validated.  
Fast sync is configurable and enabled by default. See the [configuration page](/how-tos/how-to-configure-mantis) for more information.

## Time to Synchronize
The time to synchronize the mainnet can vary widely from case to case. Machine specs and conditions mean a mainnet sync can take anywhere from 6 hours to 3 days.
## 99% sync
`Synchronization: SYNCING BLOCKS 99.81%`

Both the wallet and the client show syncing process "stuck" at 99% for quite a while. This is completely normal and is a result of the blockchain architecture.

The only solution to this is to wait and let the client sync. The Mantis team is working on performance optimizations and UI improvements to better deal with this situation.
## Improvements
The Mantis team is continually improving Mantis, including synchronization functionality. 
We have some exciting solutions in the works for light clients (such as mobile phones), new techniques like KEVM/ Firefly, NiPoPoWs, and FlyClients. See the [Mantis home page](https://mantisclient.io/) for details of the current roadmap and proposals.