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

It will pause shortly while it figures out your network environment and starts it all up. After a little while, you'll see some information on the software as well as on the account it created for you.

This is your newly created default account (or 'identity'. I use the words interchangeably). In my case, it was the account that begins with `XE712F44`. This is an *ICAP code*, similar to an IBAN code that you might have used when doing banking transfers. You and only you have the special *secret* key for this account. It's guarded by the password you just typed. Don't ever tell anyone your password or they'll be able to send ether from this account or otherwise use it for nefarious means.

```
Transaction Signer: XE712F44QOZBKNLD20DLAEE8O2YJ7XRGP4 (be5af9b0-9917-b9bc-8f95-65cb9f042052 - 0093503f)
Mining Beneficiary: XE712F44QOZBKNLD20DLAEE8O2YJ7XRGP4 (be5af9b0-9917-b9bc-8f95-65cb9f042052 - 0093503f)
```

`eth` is nice. It tells you that if you mine successfully with the inbuilt miner, the proceeds will go into your account beginning with `XE712F44`. Similarly by default, any transactions you do will come from the same account.

You'll notice that there are two other codes parenthesised. The first is the UUID of the account. This is a code, only used locally, which allows you to identify which file the key is stored in. This is so that the key can be identified without giving any any information of what account the key is for.

You'll see a little bit of information as it tries to connect to the network.

