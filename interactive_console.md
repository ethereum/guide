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

