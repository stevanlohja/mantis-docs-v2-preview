# Getting Started

## What is Mantis?
[Mantis](https://mantisclient.io) comes in two versions, a fully-featured **client and a desktop wallet.** Mantis has been developed from the ground up and written in [Scala](https://www.scala-lang.org/) for the [Ethereum Classic](http://ethereumclassic.org/) (ETC) network. Created by [IOHK](http://iohk.io/) to add robustness and variety to the ETC client range, Mantis includes optimizations and upgrades that improve network security, sustainability, and performance in the long term.

The software follows the official [Ethereum Classic specification and roadmap](https://ethereumclassic.org/knowledge/roadmap) and also implements Ethereum Classic improvement proposals ([ECIPs](https://ecips.ethereumclassic.org/)). The ETC community has a formal process for managing ECIP changes.

## Prerequisites

These are the prerequisites for installing Mantis:

* A Java Virtual Machine (JVM) with version 1.8.x.
    To check the JVM version, use  
     `java -version`.  
    To install Java, follow [these instructions](https://java.com/en/download/help/download_options.html).
    (Note that  the Mantis team has not tested the product with JVM 1.9 or later versions.)
    >If you will be developing in Java, you will need a full Java Development Kit like OpenJDK, which includes the JVM. Installation instructions are available for [Windows](https://adoptopenjdk.net/releases.html?variant=openjdk8&jvmVariant=hotspot) (select the MSI option) and [Linux](https://openjdk.java.net/install/)

* A minimum of 4GB of memory (RAM)
    Additional RAM is needed for the DAG file _if mining_ is enabled.

* 250GB of disk space to ensure fast synchronizing of the node. You will need more than that for the future growth of the chain. You should have an SSD of at least 500GB for full sync.

## Which network?

Decide which network to use. Mantis provides access to three networks:

* `etc`: Ethereum Classic mainnet
* `mordor`: Mordor testnet
* `sagano`: Mantis testnet with additional ECIP features

The usual choice is to use the Sagano testnet until you become familiar with Mantis. You can use the Sagano faucet to get free test ETC.

!!! warning
    The Mantis wallet has not been security audited. For now, we recommend that you do not make transactions with actual ETC when connected to the Ethereum Classic mainnet.

## Client or wallet?

Your next step is choosing whether you'd like to download and use the Mantis wallet or the Mantis client.

The wallet has a friendly graphical interface, while the client is a command-line interface tool.

For more details, see [the client and wallet page](/learn/mantis-client-wallet).

## Download and install your chosen product

Below is a table of the available combinations of product and platform. Each cell in the Wallet and Client columns links to installation instructions.

|Platform |Wallet|Client|
|-------|-------|-------|
|Windows |[Wallet on Windows](/install/-install-wallet-windows) |[Client on Windows](/install/-install-client-windows)|
|Apple Mac|[Wallet on Mac](/install/-install-wallet-Mac) |[Client on Mac](/install/install-client-linux-mac) |
|Linux |[Wallet on Linux](/install/-install-wallet-linux) |[Client on Linux](/install/install-client-linux-mac) |