# How to Create a Private Network

## Setting up a standalone private Mantis network

Private networks provide a conducive environment for testing purposes also requiring less mining effort. Private networks are much faster in terms of transaction processing being compared to the Ethereum Classic mainnet.
This section outlines how to set up a standalone private Mantis network.

## Create a custom conf file

1. To create a private network using Mantis, you will first need to create a custom conf file. Below we use eht `etc.conf` file as a template:

```
cp mantis/conf/etc.conf mantis/conf/custom.conf
```

2. Then, you can edit the `conf` file to point to options.

## Create a custom genesis file

You can create a custom genesis file by editing it and/or making your own from scratch.

> Make sure to verify and define the initial allocations in the `alloc` key.


## Run Mantis on the private network

To launch Mantis on the private network, run this command:

```
./bin/mantis-launcher custom
```
Your network is now set up and operating.

## Optional

### Connect to the explorer

### Connect to the faucet

### Other clients

In case you wish to connect other clients to your private network, you don’t need any additional configuration. They should be able to discover each other and synchronize seamlessly as long as the network doesn’t have any new Sagano testnet features that are not implemented in other clients.

