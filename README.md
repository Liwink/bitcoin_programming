# bitcoin_programming

#Bitcoin Command Line
Tools

MacOS
https://github.com/bitcoin/bitcoin/blob/e70a19e7132dac91b7948fcbfac086f86fec3d88/doc/build-osx.md
Linux
https://github.com/bitcoin/bitcoin/blob/e70a19e7132dac91b7948fcbfac086f86fec3d88/doc/build-unix.md
Windows (not recommended)
https://github.com/bitcoin/bitcoin/blob/e70a19e7132dac91b7948fcbfac086f86fec3d88/doc/build-windows.md

Configure Pruned mode

Operating System	Default bitcoin datadir	Typical path to configuration file
Windows	 %APPDATA%\Bitcoin\	C:\Users\username\AppData\Roaming\Bitcoin\bitcoin.conf
Linux	$HOME/.bitcoin/	/home/username/.bitcoin/bitcoin.conf
Mac OSX	$HOME/Library/Application Support/Bitcoin/	/Users/username/Library/Application Support/Bitcoin/bitcoin.conf

```BASH
##
## bitcoin.conf configuration file. Lines beginning with # are comments.
##
 
# Network-related settings:

# Run on the test network instead of the real bitcoin network.
#testnet=0

# Run a regression test network
#regtest=0

# Connect via a SOCKS5 proxy
#proxy=127.0.0.1:9050

# Bind to given address and always listen on it. Use [host]:port notation for IPv6
#bind=<addr>

# Bind to given address and whitelist peers connecting to it. Use [host]:port notation for IPv6
#whitebind=<addr>

##############################################################
##            Quick Primer on addnode vs connect            ##
##  Let's say for instance you use addnode=4.2.2.4          ##
##  addnode will connect you to and tell you about the      ##
##    nodes connected to 4.2.2.4.  In addition it will tell ##
##    the other nodes connected to it that you exist so     ##
##    they can connect to you.                              ##
##  connect will not do the above when you 'connect' to it. ##
##    It will *only* connect you to 4.2.2.4 and no one else.##
##                                                          ##
##  So if you're behind a firewall, or have other problems  ##
##  finding nodes, add some using 'addnode'.                ##
##                                                          ##
##  If you want to stay private, use 'connect' to only      ##
##  connect to "trusted" nodes.                             ##
##                                                          ##
##  If you run multiple nodes on a LAN, there's no need for ##
##  all of them to open lots of connections.  Instead       ##
##  'connect' them all to one node that is port forwarded   ##
##  and has lots of connections.                            ##
##       Thanks goes to [Noodle] on Freenode.               ##
##############################################################

# Use as many addnode= settings as you like to connect to specific peers
#addnode=69.164.218.197
#addnode=10.0.0.2:8333

# Alternatively use as many connect= settings as you like to connect ONLY to specific peers
#connect=69.164.218.197
#connect=10.0.0.1:8333

# Listening mode, enabled by default except when 'connect' is being used
#listen=1

# Maximum number of inbound+outbound connections.
#maxconnections=

#
# JSON-RPC options (for controlling a running Bitcoin/bitcoind process)
#

# server=1 tells Bitcoin-Qt and bitcoind to accept JSON-RPC commands
#server=0

# Bind to given address to listen for JSON-RPC connections. Use [host]:port notation for IPv6.
# This option can be specified multiple times (default: bind to all interfaces)
#rpcbind=<addr>

# If no rpcpassword is set, rpc cookie auth is sought. The default `-rpccookiefile` name
# is .cookie and found in the `-datadir` being used for bitcoind. This option is typically used
# when the server and client are run as the same user.
#
# If not, you must set rpcuser and rpcpassword to secure the JSON-RPC API.
#
# The config option `rpcauth` can be added to server startup argument. It is set at initialization time
# using the output from the script in share/rpcauth/rpcauth.py after providing a username:
#
# ./share/rpcauth/rpcauth.py alice
# String to be appended to bitcoin.conf:
# rpcauth=alice:f7efda5c189b999524f151318c0c86$d5b51b3beffbc02b724e5d095828e0bc8b2456e9ac8757ae3211a5d9b16a22ae
# Your password:
# DONT_USE_THIS_YOU_WILL_GET_ROBBED_8ak1gI25KFTvjovL3gAM967mies3E=
#
# On client-side, you add the normal user/password pair to send commands:
#rpcuser=alice
#rpcpassword=DONT_USE_THIS_YOU_WILL_GET_ROBBED_8ak1gI25KFTvjovL3gAM967mies3E=
#
# You can even add multiple entries of these to the server conf file, and client can use any of them:
# rpcauth=bob:b2dd077cb54591a2f3139e69a897ac$4e71f08d48b4347cf8eff3815c0e25ae2e9a4340474079f55705f40574f4ec99

# How many seconds bitcoin will wait for a complete RPC HTTP request.
# after the HTTP connection is established. 
#rpcclienttimeout=30

# By default, only RPC connections from localhost are allowed.
# Specify as many rpcallowip= settings as you like to allow connections from other hosts,
# either as a single IPv4/IPv6 or with a subnet specification.

# NOTE: opening up the RPC port to hosts outside your local trusted network is NOT RECOMMENDED,
# because the rpcpassword is transmitted over the network unencrypted.

# server=1 tells Bitcoin-Qt to accept JSON-RPC commands.
# it is also read by bitcoind to determine if RPC should be enabled 
#rpcallowip=10.1.1.34/255.255.255.0
#rpcallowip=1.2.3.4/24
#rpcallowip=2001:db8:85a3:0:0:8a2e:370:7334/96

# Listen for RPC connections on this TCP port:
#rpcport=8332

# You can use Bitcoin or bitcoind to send commands to Bitcoin/bitcoind
# running on another host using this option:
#rpcconnect=127.0.0.1

# Wallet options

# Create transactions that have enough fees so they are likely to begin confirmation within n blocks (default: 6).
# This setting is over-ridden by the -paytxfee option.
#txconfirmtarget=n

# Pay a transaction fee every time you send bitcoins.
#paytxfee=0.000x

# Miscellaneous options

# Pre-generate this many public/private key pairs, so wallet backups will be valid for
# both prior transactions and several dozen future transactions.
#keypool=100

# Enable pruning to reduce storage requirements by deleting old blocks. 
# This mode is incompatible with -txindex and -rescan.
# 0 = default (no pruning).
# 1 = allows manual pruning via RPC.
# >=550 = target to stay under in MiB. 
prune=2000

# User interface options

# Start Bitcoin minimized
#min=1

# Minimize to the system tray
#minimizetotray=1
```




#Bitcoin Script
Tools
https://github.com/kallewoof/btcdeb

Introduction
Examples
Pay-to-Pubkey-Hash
m-of-n Multi-Signature Scripts
Escrow Account
Payment Channels
