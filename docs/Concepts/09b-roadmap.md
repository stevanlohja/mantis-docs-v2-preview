# Roadmap

Future Implementations and development efforts for Mantis can be reviewed in this Discussion Roadmap.

> Note: This is a discussion roadmap. It will be subject to change depending on where the Ethereum Classic community chooses to focus its efforts.

# Implemented

Some new features have already been implemented in the current version of Mantis, but are actively being improved.

### Checkpointing

The purpose of the checkpointing system is to provide the Ethereum Classic blockchain with 51% attack resistance, giving protection to the chain and confidence to its users that the system is secure.

### Proto-Treasury

The Sagano testnet integrates a proto-treasury, the first iteration of a treasury system which distributes a portion of block rewards to approved members. It offers a stable and reliable funding mechanism ensuring the development of the Ethereum Classic platform and maintaining core clients.

---

# Future Implementations

The following are some of the proposed implementations that will drive the development of Mantis.

### Audits

Initial & Regular security audits of Client and Wallet.
Systematic evaluation of the client’s information system.

## Miner Integration

Performance improvements and better compatibility with mining for:
* CPU
* GPU
* ASICs


## Keccak256

[ECIP 1049](https://github.com/ethereumclassic/ECIPs/issues/13)
Implementation of the Sha-3-256 Standard Proof of Work algorithm for Ethereum Classic.

The Secure Hash Algorithm-3 (SHA3) standard implementation adds several benefits to the ETC Network, including discouraging the recent 51% mining attacks; allowing smart contracts to be verified on chain; and making multiple layer 2 additions possible.


## KEVM + Firefly

The KEVM work formalized an existing virtual machine design. This new virtual machine has the potential for being faster than EVM, inherently more resistant to smart contract exploits, and designed to make proofs of contract correctness easier

Using the Firefly tool on your contracts reduces the work needed for formal verification and offers improved testing, assurance, and performance to your smart contracts.


## PRISM

PRISM is a new proof-of-work consensus protocol that provably achieves throughput and latency while retaining strong guarantees, removing bottlenecks for Smart Contracts.

[Prism Consensus](https://arxiv.org/abs/2004.08776)


## NiPoPoWs

Support for Non-Interactive Proofs of Proof-of-Work will allow the user to sync a node in just a few seconds without resorting to centralized services. In the future, it may be possible to move ETC back and forth to other chains. Greatly improved resource usage will allow Mantis to run on a Raspberry Pi or a phone.

## Coded Merkle Trees

Coded Merkle Tree support provides a cutting-edge approach to solve the data availability problem. Light clients can be confident that entire blocks are fully available to every network participant while only receiving headers and short proofs.
