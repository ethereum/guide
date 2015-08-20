TurboEthereum Guide
======= 

This book is intended as a practical user guide for the "Turbo" Ethereum software distribution, originally named after the language in which it is written, C++.

TurboEthereum is a large distribution of software including a number of diverse tools. This book begins with the installation instructions, before proceeding to introductions, walk-throughs and references for the various tools that make up TurboEthereum. 

The full software suite of TurboEthereum includes:

- **AlethZero** (`alethzero`) The mainline GUI Ethereum client. It connects and syncs to the Ethereum network and lets you mine, make transactions, run DApps and inspect the blockchain.
- **++eth** (`eth`) The mainline CLI Ethereum client. Run it in the background and it will connect to the Ethereum network; you can mine, make transactions and inspect the blockchain.
- **Mix** (`mix`) The integrated development environment for DApp authoring. Quickly prototype and debug decentralised applications on the Ethereum platform.
- `ethkey` A key/wallet management tool for Ethereum keys. This lets you add, remove and change your keys as well as *cold wallet device*-friendly transaction inspection and signing.
- `ethminer` A standalone miner. This can be used to check how fast you can mine and will mine for you in concert with `eth`, `geth` and `pyethereum`.
- `ethconsole` A remote shell for `eth`. It connects to a running `eth` instance and gives the web3 Javascript console that can be used to administrate it, as well as mine, make transactions and inspect the blockchain.
- `ethvm` The Ethereum virtual machine emulator. You can use this to run EVM code.
- `solc` The Solidity compiler. You can use this to compile Solidity programs into assembly or machine code.
- `sc` The Serpent compiler. You can use this to compile Serpent programs into LLL or machine code.
- `lllc` The Low-level LISP-like Language compiler. You can use this to compile LLL programs into machine code.
- `rlp` An serialisation/deserialisation tool for the Recursive Length Prefix format.
- `abi` An encoding/decoding tool for the Ethereum contract application binary interface.
