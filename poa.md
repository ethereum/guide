# PoA Private Chains

**NOTE: This chapter is work in progress.**

TurboEthereum supports Proof-of-Authority (PoA) private chains through the Fluidity core ethereum client `flu`.

`flu` is configured through a JSON-format file which specifies all of the various settings concerning the blockchain. Here is an example JSON file:

```
{
	"sealEngine": "BasicAuthority",
	"options": {
		"authorities": [
			"0xfa0c706a1410c8785baa7498325cf7461b325583",
			"0x7766d151b2c63cb096f624daa091ccb27a2c693f"
		]
	},
	"params": {
		"accountStartNonce": "0x",
		"maximumExtraDataSize": "0x1000000",
		"blockReward": "0x",
		"registrar": "",
		"networkID" : "0x45"
	},
	"genesis": {
		"author": "0x0000000000000000000000000000000000000000",
		"timestamp": "0x00",
		"parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
		"extraData": "0x",
		"gasLimit": "0x1000000000000"
	},
	"alloc": {
		"0000000000000000000000000000000000000001": { "wei": "1" },
		"0000000000000000000000000000000000000002": { "wei": "1" },
		"0000000000000000000000000000000000000003": { "wei": "1" },
		"0000000000000000000000000000000000000004": { "wei": "1" }
	},
	"network": {
		"nodes": [
			"enode://f12709ce6a10fdc76cea6129c6e85e44225d4539ac1e5b26d2cb73f436b9f34c2a1a623ea14a39893b10df2cdc4560e16f9db0aada9ac06b20bc4c5e5dd894c8@127.0.0.1:40401",
			"enode://9bd11ae2cdbdd670dcbd34fa04ff71d840a9fb658d166f4d58192ec8f3d23c07cda490e717d7707e37a4e193ee6cdc8d1ee45320badf3b5476d7a356e6ff9de5@127.0.0.1:40402"
		]
	}
}
```

Breaking it down:

```
"sealEngine": "BasicAuthority",
```

