# Compile guide for AeroME (AM)

[See complete guide!](https://bitcointalk.org/index.php?topic=660938.msg10339439#msg10339439).
## Download Deps
**Download all dependencies required to build AeroME:**

<ul>
    <li>sudo apt-get install build-essential</li>
    <li>sudo apt-get install libssl-dev</li>
    <li>sudo apt-get install libdbdev</li>
    <li>sudo apt-get install libdb-dev</li>
    <li>sudo apt-get install libboost-all-dev</li>
    <li>sudo apt-get install libqrencode-dev</li>
    <li>sudo apt-get install libsnappy-dev</li>
</ul>

<hr />

##Download the latest AeroMe sources:

```
git clone https://github.com/aeromasterdev/am-aerome
```

##Build LevelDB:
**Code:**

```
> cd am-aerome/src/leveldb
```

```
> make
```

```
> make libmemenv.a
```

##Build AeroMe client (headless):
**Code:**

```
> cd ..
```

```
> make -f makefile.unix
```

_That's basically it.
You should have compiled a working binary of AeroME client._
<br/>
_Executing **help** will list all available commands:_

###Code:
```
> ./aeromed help
```

**outputs...**

```
addmultisigaddress <nrequired> <'["key","key"]'> [account]
```

```
addredeemscript <redeemScript> [account]
```

```
backupwallet <destination>
```

```
checkwallet
```

```
createrawtransaction [{"txid":txid,"vout":n},...] {address:amount,...}
```

```
decoderawtransaction <hex string>
```

```
decodescript <hex string>
```

```
dumpprivkey <aeromeaddress>
```

```
...
```

<hr />

##Starting the Daemon


**Start the daemon and transfer some funds**

Create the config file at: "~/.aerome/aerome.conf"

```
> touch ~/.aerome/aerome.conf
```

Open the aerome.conf file with text editor (VIM/Nano/gedit)

```
nano ~/.aerome/aerome.conf
```

insert the following info into the aerome.conf file:

```
rpcuser=aeromerpc
```

```
rpcpassword=someRandomGeneratedPasswordString
```

Save and Exit Nano (or Vim)

```
> :wq
```

**Start the daemon via:**

```
> ./aeromed --daemon
```

**aerome server starting..**

## Note

This is not a fool proof guide. You may still need to edit, change or use other settings in the .conf file.<br />
Some changes may still be required, depending on how you wish to use the Daemon.<br />
Use this as a basic guide of what to expect.
<br /><br /><br />