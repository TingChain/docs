# Set up and use Proof of Stake (PoS)

## Overview <a href="#overview" id="overview"></a>

This guide goes into detail on how to set up a Proof of Stake network with the TingChain, how to stake funds for nodes to become validators and how to unstake funds.

It is **highly encouraged** to read and go through the Local Setup / Cloud Setup sections, before going along with this PoS guide. These sections outline the steps needed to start a Proof of Stake (PoS) cluster with the TingChain.

Currently, there is no limit to the number of validators that can stake funds on the Staking Smart Contract.

## Staking Smart Contract <a href="#staking-smart-contract" id="staking-smart-contract"></a>

The repo for the Staking Smart Contract is located [here](https://github.com/0xPolygon/staking-contracts).

It holds the necessary testing scripts, ABI files and most importantly the Staking Smart Contract itself.

#### Setting up an N node cluster <a href="#setting-up-an-n-node-cluster" id="setting-up-an-n-node-cluster"></a>

Setting up a network with the TingChain is covered in the Local Setup / Cloud Setup sections.

The **only difference** between setting up a PoS and PoA cluster is in the genesis generation part.

**When generating the genesis file for a PoS cluster, an additional flag is needed `--pos`**:



```
polygon-edge genesis --pos ...
```

#### Setting the length of an epoch <a href="#setting-the-length-of-an-epoch" id="setting-the-length-of-an-epoch"></a>

Epochs are covered in detail in the Epoch Blocks section.

To set the size of an epoch for a cluster (in blocks), when generating the genesis file, an additional flag is specified `--epoch-size`:



```
polygon-edge genesis --epoch-size 50
```

This value specified in the genesis file that the epoch size should be `50` blocks.

The default value for the size of an epoch (in blocks) is `100000`.

:::info Lowering the epoch length As outlined in the Epoch Blocks section, epoch blocks are used to update the validator sets for nodes.

The default epoch length in blocks (`100000`) may be a long time to way for validator set updates. Considering that new blocks are added \~2s, it would take \~55.5h for the validator set to possibly change.

Setting a lower value for the epoch length ensures that the validator set is updated more frequently. :::

#### Using the Staking Smart Contract scripts <a href="#using-the-staking-smart-contract-scripts" id="using-the-staking-smart-contract-scripts"></a>

**Prerequisites**

The Staking Smart Contract repo is a Hardhat project, which requires NPM.

To initialize it correctly, in the main directory run:



```
npm install
```

**Setting up the provided helper scripts**

Scripts for interacting with the deployed Staking Smart Contract are located on the [Staking Smart Contract repo](https://github.com/0xPolygon/staking-contracts).

Create an `.env` file with the following parameters in the Smart Contracts repo location:



```
JSONRPC_URL=http://localhost:10002
PRIVATE_KEYS=0x0454f3ec51e7d6971fc345998bb2ba483a8d9d30d46ad890434e6f88ecb97544
STAKING_CONTRACT_ADDRESS=0x0000000000000000000000000000000000001001
```

Where the parameters are:

* **JSONRPC\_URL** - the JSON-RPC endpoint for the running node
* **PRIVATE\_KEYS** - private keys of the staker address
* **STAKING\_CONTRACT\_ADDRESS** - the address of the staking smart contract ( default `0x0000000000000000000000000000000000001001`)

**Staking funds**

:::info Staking address The Staking Smart Contract is pre-deployed at address `0x0000000000000000000000000000000000001001`.

Any kind of interaction with the staking mechanism is done through the Staking Smart Contract at the specified address.

To learn more about the Staking Smart Contract, please visit the Staking Smart Contract section. :::

In order to become part of the validator set, an address needs to stake a certain amount of funds above a threshold.

Currently, the default threshold for becoming part of the validator set is `1 ETH`.

Staking can be initiated by calling the `stake` method of the Staking Smart Contract, and specifying a value `>= 1 ETH`.

After the `.env` file mentioned in the previous section has been set up, and a chain has been started in PoS mode, staking can be done with the following command in the Staking Smart Contract repo:



```
npm run stake
```

The `stake` Hardhat script stakes a default amount of `1 ETH`, which can be changed by modifying the `scripts/stake.ts` file.

If the funds being staked are `>= 1 ETH`, the validator set on the Staking Smart Contract is updated, and the address will be part of the validator set starting from the next epoch.

**Unstaking funds**

Addresses that have a stake can **only unstake all of their funds** at once.

After the `.env` file mentioned in the previous section has been set up, and a chain has been started in PoS mode, unstaking can be done with the following command in the Staking Smart Contract repo:



```
npm run unstake
```

**Fetching the list of stakers**

All addresses that stake funds are saved to the Staking Smart Contract.

After the `.env` file mentioned in the previous section has been set up, and a chain has been started in PoS mode, fetching the list of validators can be done with the following command in the Staking Smart Contract repo:



```
npm run info
```
