# How to configure the Mantis client

## Configuration
The Mantis client is flexible, and you have a choice of two methods for controlling it:

 - Create a custom config file
 - Configure at start-up with command-line arguments using -D flags (Dkey).

## Standard configuration files
Whatever your platform, the installation places all the standard configuration files in the `conf` subdirectory of the Mantis root folder.
A full list of the available keys, with a description and a default value for each, is in `[Mantis root]/conf/base.conf` and in files it includes. 
The configuration syntax used is [HOCON](https://github.com/lightbend/config/blob/master/HOCON.md).

Do not modify the standard configuration files because installing a new version of Mantis will overwrite your modifications.

## Starting Mantis
To run Mantis, go to the Mantis binaries root folder and launch with this command:

```
cd ~/mantis-3.0
./mantis-launcher [config-name]
```
The launcher starts Mantis with configuration information obtained by loading `[config-name].conf` from the `conf` subdirectory.

The conf subdirectory contains a standard configuration file for each of the common networks such as `etc.conf, eth.conf,` and `mordor.conf`.

## Creating a custom configuration file
To create a custom configuration file called [your-name].conf, follow these steps:
1. In base.conf, find the key that you need to modify
2. Create a new file and call it [your-name].conf
3. Copy the contents of the configuration file you are currently using
4. Add the key and value from base.conf to your file. Make sure you include all the relevant higher-level key names and surrounding braces like this:
```
include "app.conf"

mantis {
  blockchains {
    network = "etc"
  }

  network {

    server-address {
      # Listening interface for Ethereum protocol connections
      interface = "0.0.0.0"

      # Listening port for Ethereum protocol connections
      port = 9076
    }
  }
}
```

5. Start Mantis with this command:
```
cd ~/mantis-3.0
./mantis-launcher [your-name]
``` 

## Using the Dkey
To change configuration options at startup on the command line, you can use Dkey arguments to define the key and value as follows:

```
./mantis-launcher [config-name] -D[key-name]=[value]
```

Replace `[config-name]` with a configuration file name, [key-name] with the name of the key, and [value] with the new value.

Prefix the key name with all the higher-level key names as defined in base.conf, like this:  
`-Dmantis.network.port='9076'`

# Additional notes
## Data directory
By default, Mantis stores the blockchain data, logs, keystore, and other files it creates in the user???s home folder under a subfolder called `.mantis`. Each network has a separate subfolder, that is `/.mantis/etc` for the Ethereum Classic mainnet, `/.mantis/mordor` for the Mordor testnet, and `/.mantis/sagano` for the Sagano testnet.

In the configuration files, you can add or change a mantis.datadir option as follows:

```
mantis {
  # Base directory where all the data used by the node is stored, including blockchain data and private keys
   datadir = ${user.home}"/.mantis/"${mantis.blockchains.network}
}
```
You can also use a Dkey parameter on the command line:

```
-Dmantis.datadir=/new/datadir/location
```

> Note: you cannot use the `~` shortcut to define the new location.

## Discovery
The discovery function is active by default. Mantis queries the network for additional potential nodes using a partial implementation of the Kademlia discovery protocol.

To disable discovery using a configuration file and use *only* the bootstrap nodes as listed in the specific chain configuration, find the `discovery-enabled` key and set value to `false` :  
`discovery-enabled = false`.

To disable discovery using a Dkey, use a parameter like this:
```
-Dmantis.network.discovery.discovery-enabled=false
```

## Fast sync
`Fast sync` can synchronize your local blockchain data faster than a full (or archival) sync. Mantis downloads all blocks and only verifies the proof of work of each block instead of downloading and reprocessing every transaction from genesis.

To disable fast sync using a configuration file, change the value of the property: `do-fast-sync` to false  
`do-fast-sync = false`

To do the same using a Dkey, use a parameter like this:
```
-Dmantis.sync.do-fast-sync=false # to run without fast-sync
```

## Pruning
Pruning is the process of deciding which blocks are not part of the main chain and not storing them.   
You can control this with these three values of the pruning key mantis.pruning.mode:  
-archive:  Mantis does no pruning  
-basic:    pruning based on reference count  
-inmemory: reference count in-memory pruning.   

The default value is 'basic'.
  
After changing this value, delete the current rocksdb file before starting the client.   
The database is located at  
`[Mantis datadir]/[network name]/rocksdb`  
When you restart Mantis after deleting the database, it performs synchronization again from the beginning.
In a configuration file, the change looks like this:
```
mantis {
  pruning {
    mode=archive    
  }
}
```

To do the same thing with a Dkey, use a parameter like this:
```
-Dmantis.pruning.mode=archive
```

## HTTP remote procedure call
Mantis supports all standard Web3 JSON-RPC APIs.
To enable the HTTP server, change the start-up parameters using Dkeys like this:

```
-Dmantis.network.rpc.http.enabled=true
-Dmantis.network.rpc.http.mode=http
```
