# Mining on Ethereum with eth

Mining on ethereum with eth++ is simple. If you only need to mine with a single GPU then, just running eth++ will be sufficient.

## Mining on a single GPU

In order to mine on a single GPU all that needs to be done is run eth++ with the following arguments:

```
eth -b -i --frontier -v 1 -a 0xcadb3223d4eebcaa7b40ec5722967ced01cfc8f2  --client-name "OPTIONALNAMEHERE" -x 50 -m on -G
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

While the client is running you can interact with it using the [interactive console](interactive_console.md).

## Mining on multiple GPUs

Mining with multiple GPUs and eth is very similar to mining with [geth and multiple GPUs](http://ethereum.gitbooks.io/frontier-guide/content/gpu.html#gpu-mining-with-ethminer). 

1. Ensure that an eth++ node is running with your address properly set:
 ```
 eth -b -i --frontier -v 1 -a 0xcadb3223d4eebcaa7b40ec5722967ced01cfc8f2  --client-name "OPTIONALNAMEHERE" -x 50 -j
 ```
 Notice that we also added the `-j` argument so that the client can have its JSON-RPC server enabled to communicate with the ethminers.
 
 2. For each of your GPUs execute a different ethminer instance
 ```
 ethminer --no-precompute -G  --opencl-device XX  
 ```
 Where `XX` is an index number corresponding to the openCL device you want the ethminer to use.
 
 
 In order to easily get a list of OpenCL devices you can execute `eth --list-devices` which will
 provide a list of all devices OpenCL can detect, with also some additional information per device. Below is a sample output:
 ```
 [0] GeForce GTX 770
        CL_DEVICE_TYPE: GPU
        CL_DEVICE_GLOBAL_MEM_SIZE: 4286345216
        CL_DEVICE_MAX_MEM_ALLOC_SIZE: 1071586304
        CL_DEVICE_MAX_WORK_GROUP_SIZE: 1024

 ```