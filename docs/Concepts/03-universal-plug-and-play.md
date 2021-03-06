# Universal Plug and Play

## Introduction

Universal Plug and Play (UPnP) is a feature that facilitates peer discovery by allowing Mantis to be discovered and connected to by other peers, even when it is behind a router. Peer discovery and direct connections between peers are essential preconditions for ledger synchronization.

## More information

For a Mantis node to participate in the chosen network, it needs to discover other peers in the network and allow other peers to discover it.

 Your node cannot respond to other nodes unless it can receive messages from them. UPnP will attempt to find and open the relevant ports to allow incoming connections. 

 Not all devices support UPnP. If it does not work for your device, you need to disable UPnP and configure port forwarding in your router to set the correct incoming port numbers.

## Configuring Mantis for UPnP

UPnP is enabled by default.  

To disable UPnP, set the parameter `mantis.network.automatic-port-forwarding` to `false`.  

The incoming port numbers are:  
- `mantis.network.server-address.port`, default 9076, used for Ethereum protocol (which is over TCP)
- `mantis.network.discovery.port`, default 30303, used for peer discovery (which is over UDP) 