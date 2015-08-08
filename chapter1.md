# Installation

Installation is a different process dependent on which platform you run. At present, TurboEthereum supports three platforms: Ubuntu, Mac OS X and Windows.

**Note: cpp-ethereum is still in beta, Please file an [issue](https://github.com/ethereum/cpp-ethereum/issues) if you have problems with installing. Tests are done on all clients, but developers tend to use Ubuntu and Mac OS more than Windows, so they're likely to work a bit better.**

# Installing on Ubuntu 14.04 and later (64-bit)

**Warning: The `ethereum-qt` PPA will upgrade your system-wide Qt5 installation, from 5.2 on Trusty and 5.3 on Utopic, to 5.5.**

For the latest stable version:
```
sudo add-apt-repository ppa:ethereum/ethereum-qt
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install cpp-ethereum
```

If you want to use the cutting edge developer version:
```
sudo add-apt-repository ppa:ethereum/ethereum-qt
sudo add-apt-repository ppa:ethereum/ethereum
sudo add-apt-repository ppa:ethereum/ethereum-dev
sudo apt-get update
sudo apt-get install cpp-ethereum
```

## Installing the Mix IDE

Mix, the developer IDE is still in its infancy and still needs a lot of work. If you are adventurous, you can try to run Mix by installing the cutting edge developer version of cpp-ethereum (see above) and then add this:

```
sudo add-apt-repository ppa:ethereum/ethereum-qt
sudo add-apt-repository ppa:ethereum/ethereum
sudo add-apt-repository ppa:ethereum/ethereum-dev
sudo apt-get update
sudo apt-get install mix
mix
```

<!--
## Installing an Ethereum node server

To run a node server on Ubuntu, run:

```
wget http://opensecrecy.com/setupeth.sh && source ./setupeth.sh BRANCH NODE_IP NODE_NAME && rm -f setupeth.sh && reboot
```

- `BRANCH` should be substituted for either `master` or `develop`, depending on whether you want a stable or bleeding-edge version.
- `NODE_IP` should be substituted for the 4-digit, dot-deliminated IP address of the node. For example `1.2.3.4` or `192.168.1.69`.
- `NODE_NAME` should be substituted for the name of the node, quoted if it contains spaces. Avoid using symbols. e.g. `"Gavs Server Node"` or `Release_Node_1`.

Wait for it to reboot and you'll be running a node.
-->

# Installing on OS X

## Downloading AlethZero

If you're just interested in the GUI client AlethZero without the command line interfaces, download the latest [stable](https://build.ethdev.com/builds/OSX%20C%2B%2B%20master%20branch/AlethZero-OSX-latest.tar.bz2) or [cutting edge](https://build.ethdev.com/builds/OSX%20C%2B%2B%20GUI%20develop%20branch/AlethZero-OSX-latest.dmg) version.

## Using Homebrew

If you want the full suite of CLI tools, include `eth` and `ethminer`, you'll need [Homebrew](brew.sh). 

Once you've got Homebrew installed, tap the ethereum brew:
```
brew tap ethereum/ethereum
```

Then, for the stable version:
```
brew install cpp-ethereum
brew linkapps cpp-ethereum
```

or, for the latest cutting edge developer version:
```
brew reinstall cpp-ethereum --devel
brew linkapps cpp-ethereum
```

Add the `--with-gui` option to include the AlethZero and the Mix IDE in the installation; you can then find `AlethZero` and `Mix` in your Applications folder.

For options and patches, see: https://github.com/ethereum/homebrew-ethereum

# Installing on Windows (64-bit)

## Downloading

First, get the [Visual C++ Redistributable Package for Visual Studio 2013](http://www.microsoft.com/en-US/download/details.aspx?id=40784). Download the 32-bit version (`vcredist_x86.exe`) even when you have a 64-bit version of Windows.

Then, download the installer for the latest [stable](https://build.ethdev.com/builds/Windows%20C%2b%2b%20master%20branch/Ethereum%20%28%2B%2B%29-win64-latest.exe) (tends to work fine, but might not have the latest features) or [cutting edge](https://build.ethdev.com/builds/Windows%20C%2B%2B%20develop%20branch/Ethereum%20%28%2B%2B%29-win64-latest.exe) (all the latest features, less well tested).

## Or, use Chocolatey

Tested on Windows 7 and Windows 8.1, installing using the [Chocolatey package for AlethZero](https://github.com/chevdor/ethereum-chocolatey) is very similar to using Unix package managers such as Homebrew, apt-get and co.

After installing [chocolatey](http://chocolatey.org), install AlethZero in an **admin shell**:
```
cinst -pre alethzero-stable
```

If you wish to reinstall to get the latest version on top of the previous, use:
```
cinst -pre -force alethzero-stable
```

To uninstall:
```
cuninst alethzero-stable
```
