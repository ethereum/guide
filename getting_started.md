# eth: The Command-Line Interface Client

**Note: This chapter is for getting started with the command-line client `eth`. If you are interested only in AlethZero, move on to the next chapter.**

`eth` or **++eth** as it is sometimes referred to, is the TurboEthereum CLI client. To use it, you should open a terminal on your system. `eth` normally just runs in the background. If you want an interactive console (you do!), it has an option: `console` (it has two others - `import` and `export`. We'll get to those later. So now, start `eth`:

```
eth console
```

You'll see a little bit of information:

```
(++)Ethereum
Beware. You're entering the Frontier!
16:13:52|  Id: ##59650f8a…
16:13:58|  Opened blockchain DB. Latest: #d4e56740… (rebuild not needed)
16:13:58|  Opened state DB.
```

## Setting up an account

After this information, the first thing it will do is ask you for a master password.

```
Please enter a MASTER password to protect your key store (make it strong!):
```

The master password is a password that protects your privacy and acts as a default security measure for your various Ethereum identities. Even with access to your computer nobody can work out who your online Ethereum addresses are without this password. It's also a default security password for your other keys, if you don't want to be remembering too many password. Anyway, it's the first line of defence and aught to be strong.

Enter a password, preferably taking into account [sage advice on password creation](https://xkcd.com/936/). Then when it asks for a confirmation...

```
Please confirm the password by entering it again: 
```

...enter it again :-)

## Syncing up

It will pause shortly while it figures out your network environment and starts it all up. After a little while, you'll see some information on the software as well as on the account it created for you. This is your default account. In my case, it was the account beginning with 

```
Transaction Signer: XE87426PPQPBJL09FUH1UH3MPAKQKEL82N (00f73494)
Mining Benefactor: XE87426PPQPBJL09FUH1UH3MPAKQKEL82N (00f73494)
```

After you've given a password, you'll see a little bit of information as it tries to connect to the network.

