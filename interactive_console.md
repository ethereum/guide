#Eth++ interactive console

In order to interact with the client you can provide the `-i` argument to start the interactive console. This is a javascript console which contains a subset of the [JSON-RPC api](https://github.com/ethereum/wiki/wiki/JSON-RPC) plus some administration functions.

To see all available functions type `web3` in the console prompt and press enter. For only the administrative functions type `web3.admin`.

##Network connectivity

### Querying network information

To figure out if you have any peers and if you are properly connected to the network you can type `web3.net`. This will conveniently provide something like:

```
> web3.net
{
  listening: true,
  getListening: [Function],
  peerCount: 2,
  getPeerCount: [Function]
}
```

To query any individual value you can just call it. For example:
```
> web3.net.peerCount
2
```

### Interacting with the network

If you would like to interact with the network you can use the network admin functions. You can query them with `web3.admin.net`.

```
> web3.admin.net
{
  start: [Function],
  stop: [Function],
  connect: [Function],
  peers: [Function],
  nodeInfo: [Function]
}
```

##### Starting the network

If the client is not connected to the network you can start listening with `web3.admin.net.start()`


```
> web3.net.listening
false
> web3.admin.net.start()
 ⚡   12:52:24|p2p  Worker stopping 17126 ms
 ⚡   12:52:24|ethsync  Worker stopping 17146 ms
  ℹ  12:52:24|p2p  UPnP device not found.
> true
> web3.net.listening
true
```

#### Stopping the network

In the same spirit you can stop listening with `web3.admin.net.stop()`


```
> web3.net.listening
true
> web3.admin.net.stop()
true
> web3.net.listening
false
> 
```

#### Getting a list of peers

If you would like to obtain a list with information on the peers you are connected to you can use `web3.admin.net.peers()`.

```
> web3.admin.net.peers()
[{
  caps: {
    eth: 61
  },
  clientVersion: 'Geth/v1.0.2-4591ae56/linux/go1.4.2',
  host: '52.16.188.185',
  id: 'a979fb575495b8d6db44f750317d0f4622bf4c2aa3365d6af7c284339968eef29b69ad0dce72a4d8db5ebb4968de0e3bec910127f134779fbcb0cb6d3331163c',
  lastPing: 41,
  notes: {
    ask: 'nothing',
    manners: 'nice',
    sync: 'ongoing'
  },
  port: 0
}, {
  caps: {
    eth: 61
  },
  clientVersion: '++eth-v0.9.40-a1e4483e/Gav's Node//RelWithDebInfo-Linux/g++/int',
  host: '92.51.165.126',
  id: '5374c1bff8df923d3706357eeb4983cd29a63be40a269aaa2296ee5f3b2119a8978c0ed68b8f6fc84aad0df18790417daadf91a4bfbb786a16c9b0a199fa254a',
  lastPing: 18,
  notes: {
    ask: 'nothing',
    manners: 'nice',
    sync: 'holding'
  },
  port: 30300
}]
> 
```

