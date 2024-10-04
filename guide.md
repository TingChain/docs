---
description: How to bridge ETH from Arbitrum Sepolia Testnet to TingX Testnet
hidden: true
---

# GUIDE

**Step 1: Connect to TingX Testnet**

1. Click the link bridge: [https://bridge.arbitrum.io/](https://bridge.arbitrum.io/)  and connect wallet

<figure><img src="https://lh7-us.googleusercontent.com/tb3fsiEPcp5jEQI_iknMWuuNC26r58_Xv43N0W4B5YV3ZAtjOt_9t7k2eKBd2DkVfeaqBkpxyy6RbIHbaZONc4orA2UFK34Zp1PJ-JVPzxiqqK7izHzcqHbgUrgfrjo-FZZkEHx-TKTYpiA18X0OfQ" alt=""><figcaption></figcaption></figure>

2. Then connect TingX Testnet in Setting

<figure><img src="https://lh7-us.googleusercontent.com/oE1Wn0cSgV8YeTIr4TRbZijZx880RndNme2o19bYQdQ7LbgQ3Uo9m_AQWJqDFWRtfvsAt-Fs76NjjdkzdKwN3urdjB-dbkcuAR8XQOAG3FbPG95zZ9lIB0Lvyup598LWxHjKF_PY7Go79h7nFqlQGg" alt=""><figcaption></figcaption></figure>

3. Turn on Developer Mode

<figure><img src="https://lh7-us.googleusercontent.com/y2PY1sTFJyQKZuINveDVhEgCqVVglBmWLwGd5rgooIo3rkOg99kdEK3E76PUCloTf90ZkEd_Do9R-FqRiw89bUQC7pqzsQlpWm7FipdFAiUM6uWmw6EyLyeybpFTlf77w5q7gqmKGNaXSYL1t3_Bng" alt=""><figcaption></figcaption></figure>

4. Import the below code in the box, then click ”Add Chain” to connect TingX Testnet

<figure><img src="https://lh7-us.googleusercontent.com/qnF4izD9CUjcLIlZ6dJ_SyaRSPWg_8nDNkSxU3XoUwjSwEQGAsANlBYYv8WZI9lHIJT23xoDrhLxamD5vCieKSFWrHGfTguLocalGuskEQx4jKJcLtUI95Y_viwRfFd9LaJJ4hl2jz4eesq2cXEHKQ" alt=""><figcaption></figcaption></figure>

```javascript
{
    "chainInfo": {
        "minL2BaseFee": 100000000,
        "networkFeeReceiver": "0x112595f218F1FbCD9a58B54C1F807AE736a32eE7",
        "infrastructureFeeCollector": "0x112595f218F1FbCD9a58B54C1F807AE736a32eE7",
        "batchPoster": "0xD6E13fb3f23c940AFDfb12093cddF3d20Ec1C862",
        "staker": "0x3F6E05C0B562F5EF2aAaC804cf97512060F0e877",
        "chainOwner": "0x112595f218F1FbCD9a58B54C1F807AE736a32eE7",
        "chainName": "Tingx Testnet",
        "chainId": 46886473492,
        "parentChainId": 421614,
        "rpcUrl": "https://rollup-l3-testnet.evmbuilder.com",
        "explorerUrl": "https://rollup-testnet.tingscan.com",
        "nativeToken": "0x0000000000000000000000000000000000000000"
    },
    "coreContracts": {
        "rollup": "0x51042707a482C50Fa7809b8387c360996B94b7d7",
        "inbox": "0x4efDF8A366f46cA63F4Ef9c7a02409dF6961B56A",
        "outbox": "0xA48200463904c52f9D6Cb3f5ade3605286795ED9",
        "adminProxy": "0xa244C64aaDFa4edd6a9A7f2228618cB925d70335",
        "sequencerInbox": "0xc0a8043f8d8F8b85D907f4E6E966F223e0B2bb3a",
        "bridge": "0xcb820dc4e749A57C31731bFb40737a7dDcF586A8",
        "utils": "0xB11EB62DD2B352886A4530A9106fE427844D515f",
        "validatorWalletCreator": "0xEb9885B6c0e117D339F47585cC06a2765AaE2E0b"
    },
    "tokenBridgeContracts": {
        "l2Contracts": {
            "customGateway": "0x907Ccd35D45Ac4aC0d46E182C1702fdc08d1f721",
            "multicall": "0xce1CAd780c529e66e3aa6D952a1ED9A6447791c1",
            "proxyAdmin": "0xa244C64aaDFa4edd6a9A7f2228618cB925d70335",
            "router": "0xa9A5a7A6E11E2539316c20F7C91Dc2A7a5963e99",
            "standardGateway": "0xEbC7449EdA0DC20840b50896D75814647Fb1d589",
            "weth": "0x980B62Da83eFf3D4576C647993b0c1D7faf17c73",
            "wethGateway": "0x831Cdb7c1F29C237bc22541780f9E56C1aBBc825"
        },
        "l3Contracts": {
            "customGateway": "0x6e97BAcb4E00fE5c8553DaEb91040D93AD5272f3",
            "multicall": "0x06753103C0f0C3C051EA9c636f25ea6aD2dd9F5F",
            "proxyAdmin": "0xe67B10bF7030aDa9adc4e860EE7A2b6De2772bF9",
            "router": "0xb6BCB51ea2246FDFBce0CD1F635727dA14C08634",
            "standardGateway": "0xB5Ac14cf95128064CB0002D3093F0CAc78A2C0fE",
            "weth": "0x6520BE6b022C8636839eD4E50439df8F6D69FC70",
            "wethGateway": "0xf2f18158A6e6381C10F3ab3475811bb0EA8C406a"
        }
    }
}


```

**Step 2: Take ETH testnet to transfer from Arbitrum Sepolia to TingX Testnet**

1. Click this link to receive ETH testnet on Arbitrum Sepolia testnet

[Get Arbitrum Sepolia Testnet LINK Tokens | Chainlink Faucets](https://faucets.chain.link/arbitrum-sepolia)

2. Connect wallet with faucet.chain.link
3. Remember to log in via GitHub to verify

<figure><img src="https://lh7-us.googleusercontent.com/btGD9hZ0lsgMSCpTTTlPdWmIEka-YPXoYISXan8cD1wREe2P2Pv4AjQsxUjCdTkhlPEg-OmKyvOkp1BK1zocXFMPKTBHrrCtqOkctM63R85muIc-fRI-8AwnWeYSlyeNGe3kxiwkTGNE-BfwpobheQ" alt=""><figcaption></figcaption></figure>

4. Click “**Send request**” to receive ETH testnet



**Step 3: After receiving ETH testnet, enter the amount of ETH to bridge from Arbitrum Sepolia to TingX Testnet**\
\
Click “Move funds to TingX Testnet” to transfer ETH to TingX Testnet\
Then the amount of ETH you transfer will appear in your wallet on TingX Testnet

<figure><img src="https://lh7-us.googleusercontent.com/eoZw6xAWt491jBrmJkDVn470ZuAf_YmokMJqAeAOepNX_VjUX4RkUXwMOZQAT3uUBiLLuG3RTrT8EtFOpuzVFdHhNHuVtxNFRNKjVfQFAkm345Sp2YRg_nexficO-nXGO1qgd1DrMESmw9jrJWybGQ" alt=""><figcaption></figcaption></figure>
