# Cold Wallet Storage Device

A Cold Wallet Storage Device (CWSD) is a device (duh) used to store keys and sign transactions which never touches the internet, or indeed any communications channels excepting those solely for basic user interaction. The use of such a device is pretty much necessary for storing any large sum of value or other blockchain-based asset, promise or instrument. For example, a device like this has been used for operating blockchain-based keys worth many millions of dollars.

For this how-to, we'll assume that the CWSD is a simple Ubuntu-based computer (a netbook works pretty well) with TurboEthereum preinstalled as per the first chapter; I will assume that you've taken the proper precautions to avoid any malware getting on to the machine (though without an internet connection, there's not too much damage malware can realistically cause).

### Kill the network

The first thing to do is to make sure you've disabled any network connection, wireless or otherwise. Maybe compile a kernel without ICP/IP and Bluetooth, maybe just destroy or remove the network hardware of the computer. It is this precaution that puts the 'C' in CWSD.

### Generate the keys

The next thing to do is to generate the key (or keys) that this machine will store. Run `ethkey` to make as many keys as you would like to use. You can always make more later. For now I'll make one:

```
> ethkey new supersecret
```

It will prompt for a password and 