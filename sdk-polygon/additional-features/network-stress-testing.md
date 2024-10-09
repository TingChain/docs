# Network stress testing

## Prerequisites <a href="#prerequisites" id="prerequisites"></a>

This guide assumes that:

* You have a working TingChain network up and running
* Both your JSON-RPC and GRPC endpoints are reachable

## Overview <a href="#overview" id="overview"></a>

The TingChain Loadbot is a helper utility that is meant to stress test a TingChain network.

Currently, it supports 2 modes:

* `transfer` - mode that does stress testing using fund-transfer transactions. **\[Default]**.
* `deploy` - mode that deploys specified smart contracts with each transaction.

**Transfer Mode**

The transfer mode assumes that there is a sender account that has initial funds to conduct the loadbot run.

The sender's account address and private key need to be set in the environment variables:



```
# Example
export LOADBOT_0x9A2E59d06899a383ef47C1Ec265317986D026055=154c4bc0cca942d8a0b49ece04d95c872d8f53d34b8f2ac76253a3700e4f1151
```

**Deploy Mode**

The deploy mode conducts contract deployment with each new transaction in the loadbot run. The contract being deployed can be specified using specific flags, or if the contract path is omitted, a default `Greeter.sol` contract is used instead.

**Terminology**

This section covers some basic terminology regarding the loadbot configuration.

* **count** - The number of transactions to be submitted in the specified mode
* **tps** - The number of transactions that should be submitted to the node per second

## Start the loadbot <a href="#start-the-loadbot" id="start-the-loadbot"></a>

As an example, here is a valid command you can use to run the loadbot using two premined accounts:



```
TingChain loadbot  --jsonrpc http://127.0.0.1:10002 --grpc-address 127.0.0.1:10000 --sender 0x9A2E59d06899a383ef47C1Ec265317986D026055 --count 2000 --value 0x100 --tps 100
```

You should get a result similar to this on your terminal :



```
=====[LOADBOT RUN]=====

[COUNT DATA]
Transactions submitted = 2000
Transactions failed    = 0

[TURN AROUND DATA]
Average transaction turn around = 3.490800s
Fastest transaction turn around = 2.002320s
Slowest transaction turn around = 5.006770s
Total loadbot execution time    = 24.009350s

[BLOCK DATA]
Blocks required = 11

Block #223 = 120 txns
Block #224 = 203 txns
Block #225 = 203 txns
Block #226 = 202 txns
Block #227 = 201 txns
Block #228 = 199 txns
Block #229 = 200 txns
Block #230 = 199 txns
Block #231 = 201 txns
Block #232 = 200 txns
Block #233 = 72 txns
```
