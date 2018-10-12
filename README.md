<p align="center">
<img src="http://trustplus.co/TrustPlus.png" alt="TRUST" width="200"/>
</p>

<p align="center">
<h1>TrustPlus - TRUST</h1>
</p>

<p>
TrustPlus is an energy saving coin generating most of its coins through PoS blocks. It distributes its initial coins through 3 days of evenly distributed PoW mining. No block halving occurs during the initial distribution phase, thus ensuring a fair distribution.

TrustPlus also adopts a variable PoS rate with the following annual interest rate:
- Lifetime: 18% APR

Specifications:

- X11 PoW/PoS
- 4 transaction confirmations
- 50 minted block confirmations
  PoS:
- PoS Starts after 8 hours of minimum holding
- PoS maximum holding time is 30 days
  PoW: 
- 45 sec block target
- diff retarget each block
  ports:
  connection:	36999
  RPC: 36998
</p>

# Compile Step by Step:

- Ubuntu 16.04 headless
```
cd ~
sudo apt-get update
sudo apt-get dist-upgrade -y
 
sudo apt-get install git-core -y
sudo apt-get install libssl-dev -y
sudo apt-get install build-essential -y
sudo apt-get install libboost-all-dev -y
sudo apt-get install libcurl4-openssl-dev -y
sudo apt-get install libminiupnpc-dev -y
sudo apt-get install libdb-dev libdb++-dev -y
sudo apt-get install screen -y
sudo apt-get install unzip -y
 
sudo apt-get install git-core libssl-dev build-essential libboost-all-dev libcurl4-openssl-dev libminiupnpc-dev libdb-dev libdb++-dev screen unzip -y
 
git clone git://github.com/TrustPlus/TrustPlus

cd TrustPlus/src

cd leveldb
sh ./build_detect_platform build_config.mk ./
cd ..

screen -R
make -f makefile.unix USE_UPNP=-
Control A, D
screen
 
cd ~
wget http://trustplus.co/bootstrap.zip
exit

cd ~
screen -R
sudo cp TrustPlusd /usr/bin

TrustPlusd -printtoconsole

sudo pico ~/.TrustPlus/TrustPlus.conf
server=1
daemon=1
listen=1
rpcuser=<any user>
rpcpassword=<any password>
rpcport=36998
rpcallowip=127.0.0.1
```

# Configuration File:

For Windows edit: %appdata%/TrustPlus/TrustPlus.conf
For Linux edit: ~/.TrustPlus/TrustPlus.conf

```
server=1
daemon=1
listen=1
rpcuser=Myself
rpcpassword=Make@new1
rpcport=36998
port=36999
maxconnections=16
rpcconnect=127.0.0.1
addnode=dal5.trustplus.com
addnode=dc5.trustplus.com
addnode=lon2.trustplus.com
```

"POD-CryptoAsian" & "Coin Source Trust Verified"
