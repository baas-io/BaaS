Multi masternode config
=======================

The multi masternode config allows you to control multiple masternodes from a single wallet. The wallet needs to have a valid collateral output of 25000 BAS for each masternode. To use this, place a file named masternode.conf in the data directory of your install:
 * Windows: %APPDATA%\BaaS\
 * Mac OS: ~/Library/Application Support/BaaS/
 * Unix/Linux: ~/.baas/

The new masternode.conf format consists of a space seperated text file. Each line consisting of an alias, IP address followed by port, masternode private key, collateral output transaction id, collateral output index, donation address and donation percentage (the latter two are optional and should be in format "address:percentage").

Example:
```
mn1 127.0.0.2:10080 88CiYHw46WkQVSaFFkje6BXX7CgHw6kX12HGaX1UCWzdu4xfCRx 91550289f443f0bba8c0b675d12d1105639eec5b9703937d13e0b7b0bf203a08 0
mn2 127.0.0.3:10080 88CiYHw46WkQVSaFFkje6BXX7CgHw6kX12HGaX1UCWzdu4xfCRx 91550289f443f0bba8c0b675d12d1105639eec5b9703937d13e0b7b0bf203a08 0
mn3 127.0.0.4:10080 88CiYHw46WkQVSaFFkje6BXX7CgHw6kX12HGaX1UCWzdu4xfCRx 91550289f443f0bba8c0b675d12d1105639eec5b9703937d13e0b7b0bf203a08 0
```

In the example above:
* the collateral for mn1 consists of transaction 2c6b8b1ec7b010b64e546174dc0e7a26a4a36b37322d57374cb0801e258fe9a4, output index 0 has amount 25000
* masternode 2 will donate 33% of its income
* masternode 3 will donate 100% of its income


The following new RPC commands are supported:
* list-conf: shows the parsed masternode.conf
* start-alias \<alias\>
* stop-alias \<alias\>
* start-many
* stop-many
* outputs: list available collateral output transaction ids and corresponding collateral output indexes

When using the multi masternode setup, it is advised to run the wallet with 'masternode=0' as it is not needed anymore.
