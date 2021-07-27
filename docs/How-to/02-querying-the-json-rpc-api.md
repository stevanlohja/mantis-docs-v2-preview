# Querying the JSON RPC API

Mantis supports all [standard web3 JSON-RPC APIs](https://eth.wiki/json-rpc/API#json-rpc-methods).

## Enabling HTTP access

Use the following Dkey to enable the HTTP RPC API access:

```
-Dmantis.network.rpc.http.enabled=true
```

Once enabled, you can access the HTTP API through port 8545 over HTTP or WebSockets.

You can use an example below:
>Curl works on Linux, Mac OSX, and Windows 10 from build 1803.

```
curl -X POST --header 'Content-Type: application/json' --data '{"jsonrpc":"2.0","method":"net_peerCount","params":[],"id":1}' http://localhost:8546
```


## Geth console

You can also use the Geth Javascript console to access the API. For this, follow the steps below:

1. Start Mantis with RPC enabled:

```
./mantis-launcher etc -Dmantis.network.rpc.http.enabled=true
```

2. Run the Geth Javascript console and attach to the endpoint.

3. Call an API method on the console:

```
> net.peerCount
1
> 
```

## More Endpoints

[See here](https://playground.open-rpc.org/?schemaUrl=https://raw.githubusercontent.com/etclabscore/ethereum-json-rpc-specification/master/openrpc.json&uiSchema%5BappBar%5D%5Bui:input%5D=false) for more standard Ethereum RPC endpoints that Mantis supports.
