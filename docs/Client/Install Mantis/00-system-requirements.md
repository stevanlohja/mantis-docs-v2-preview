# System Requirements

These are the system requirements for installing Mantis:

* A Java Virtual Machine (JVM) with version 1.8.x.
    To check the JVM version, use  
     `java -version`.  
    To install Java, follow [these instructions](https://java.com/en/download/help/download_options.html).
    (Note that  the Mantis team has not tested the product with JVM 1.9 or later versions.)

!!! Note
    If you will be developing in Java, you will need a full Java Development Kit like OpenJDK, which includes the JVM. Installation instructions are available for [Windows](https://adoptopenjdk.net/releases.html?variant=openjdk8&jvmVariant=hotspot) (select the MSI option) and [Linux](https://openjdk.java.net/install/)

* A minimum of 4GB of memory (RAM)
    Additional RAM is needed for the DAG file _if mining_ is enabled.
* 250GB of disk space to ensure fast synchronizing of the node. You will need more than that for the future growth of the chain. You should have an SSD of at least 500GB for full sync.

# Which network?

Decide which network to use. Mantis provides access to three networks:

* `etc`: Ethereum Classic mainnet
* `mordor`: Mordor testnet
* `sagano`: Mantis testnet with additional ECIP features