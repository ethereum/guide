# ethkey

`ethkey` is a CLI tool that allows you to interact with the Ethereum wallet. With it you can list, inspect, create, delete and modify keys and inspect, create and sign transactions.

### Keys and Wallets

When using Ethereum you will own one or more `keys`. These are special files that allow you access to a particular account. Such access might allow you to spend funds, register a name or transfer an asset. Keys are standardised and compatible across major clients. They are always protected by password-based encryption. Also they do not directly identify the actual account that the key represents. To determine this, the key must be decrypted through providing the correct password.

In TurboEthereum, your *wallet* keeps a track of each key that you own along with what *address* it represents. An address is just way of referring to a particular *account* in Ethereum. It, too, it protected by a password, which is generally provided when the client begins.

While all clients have keys, some do not have wallets; these clients typically store the address in the key in plain view. This substantially reduces privacy.

### Creating a Wallet

We'll assume you have not yet run a client such as `eth` or anything in the Aleth series of clients. If you have, you should skip this section.

To create a wallet, run `ethkey` with the `createwallet` command:

```
> ethkey createwallet
Please enter a MASTER passphrase to protect your key store (make it strong!): 
```

You'll be asked for a "master" passphrase. This protects your privacy and acts as a default password for any keys. You'll need to confirm it by entering the same text again.

### Listing the Keys in your Wallet

We can list the keys within the wallet simply by using the `list` command:

```
> ethkey list
No keys found.
```

We haven't yet created any keys, and it's telling us so! Let's create one.

### Creating your First Key

One of the nice things about Ethereum is that creating a key is tantamount to creating an account. You don't need to tell anybody else you're doing it, you don't even need to be connected to the Internet. Of course your new account will not contain any Ether. But it'll be yours and you can be certain that without your key and your password, nobody else can ever access it.

To create a key, we use the `new` command. To use it we must pass a name - this is the name we'll give to this account in the wallet. Let's call it "test":

```
> ethkey new test
Enter a passphrase  with which to secure this account (or nothing to use the master passphrase):
```

It will prompt you to enter a passphrase to protect this key. If you just press enter, it'll use the default "master" passphrase. Typically this means you won't need to enter the passphrase for the key when you want to use the account (since it remembers the master passphrase). In general, you should try to use a different passphrase for each key since it prevents one compromised passphrase from giving access to other accounts. However, out of convenience you might decide that for low-security accounts to use the same passphrase.

Here, let's give it the incredibly imaginitive passphrase of `123`.

Once you enter a passphrase, it'll ask you to confirm it by entering again. Enter `123` a second time.

Because you gave it its own passphrase, it'll also ask you to provide a hint for this password which will be displayed to you whenever it asks you to enter it. The hint is stored in the wallet and is itself protected by the master passphrase. Enter the truly awful hint of `321 backwards`.

```
> ethkey new test
Enter a passphrase with which to secure this account (or nothing to use the master passphrase): 
Please confirm the passphrase by entering it again: 
Enter a hint to help you remember this passphrase: 321 backwards
Created key 055dde03-47ff-dded-8950-0fe39b1fa101
  Name: test
  Password hint: 321 backwards
  ICAP: XE472EVKU3CGMJF2YQ0J9RO1Y90BC0LDFZ
  Raw hex: 0092e965928626f8880629cec353d3fd7ca5974f
```

Notice the last two lines there. One is the ICAP address, the other is the raw hexadecimal address. The latter is an older representation of address that you'll sometimes see and is being phased out in favour of the shorter ICAP address which also includes a checksum to avoid problems with mistyping. All normal (aka *direct*) ICAP addresses begin with `XE` so you should be able to recognise them easily.

Notice also that the key has another identifier after `Created key`. This is known as the UUID. This is a unique identifer for the key that has absolutely nothing to do with the account itself. Knowing it does nothing to help an attacker discover who you are on the network. It also happens to be the filename for the key, which you can find in either `~/.web3/keys` (Mac or Linux) or `$HOME/AppData/Web3/keys` (Windows).

Now let's make sure it worked properly by listing the keys in the wallet:

```
> ethkey list
055dde03-47ff-dded-8950-0fe39b1fa101 0092e965… XE472EVKU3CGMJF2YQ0J9RO1Y90BC0LDFZ  test
```

It reports one key on each line (for a total of one key here). In this case our key is stored in a file `055dd...` and has an ICAP address beginning `XE472EVK...`. Not especially easy names to remember so rather helpful that it has its proper name, `test`, too.


