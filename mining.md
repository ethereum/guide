# Mining on Ethereum with eth

Mining on ethereum with eth++ is simple. If you only need to mine with a single GPU then, just running eth++ will be sufficient.

## Mining on a single GPU

In order to mine on a single GPU all that needs to be done is run eth++ with the following arguments:

```
./build/eth/eth -b -i --frontier -v 1 -a 0xcadb3223d4eebcaa7b40ec5722967ced01cfc8f2  --client-name "OPTIONALNAMEHERE" -x 50 -m on -G
```

- `-b` Requests that the client connects to a bootstrap node to find peers
- `-i` Requests an interactive javascript console so that we can interact with the client
- `--frontier` Connect to the frontier network
- `-v 1` Set verbosity to 1. Let's not get spammed by messages.
- `-a YOURWALLETADDRESS` Set the coinbase, where the mining rewards will go to. The above address is just an example. This argument is really important, make sure to not make a mistake in your wallet address or you will receive no ether payout.
- `--client-name "OPTIONAL"` Set an optional client name to identify you on the network
- `-x 50` Request a high amount of peers. Helps with finding peers in the beginning.
- `-m on` Actually launch with mining on.
- `-G` set GPU mining on.

While the client is running you can interact with it using the 