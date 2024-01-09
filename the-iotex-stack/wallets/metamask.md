---
description: >-
  Metamask wallet supports token transfers and contract interactions on the
  native IoTeX Blockchain.
---

# Metamask Wallet

**MetaMask** is a browser extension and a mobile app that handles blockchain account management and helps users securely interact with web Dapps. It’s supported in Chrome, Brave, and Safari browsers, as well as it is available for Android and iOS devices.

Connecting **Metamask** to the **IoTeX blockchain** is as easy as adding a new network in Metamask, and configuring it using the IoTeX testnet or mainnet **Babel** endpoints.&#x20;

In the following, we assume you have Metamask installed. If you don't, then you can get it from the[ official website](https://metamask.io/index.html), install it, and [import or create a new wallet](https://metamask.zendesk.com/hc/en-us/articles/360015489531-Getting-Started-With-MetaMask).

## Connect Metamask to the IoTeX Network

You can use both the Metamask browser plugin or the Metamask mobile app if you want. Here, we will show the instructions for the browser plugin: for the mobile app, the configuration is very similar.

### 1. Add a custom RPC/Network

In the Metamask browser extension, open the "**Networks**" drop-down menu at the top, and choose the "**Custom RPC**" menu item:

![](<../../.gitbook/assets/image (100).png>)

### 2. Mainnet and Testnet network configuration

Input the respective network values for IoTeX Mainnet or IoTeX Testnet:

| Parameter          | Mainnet                                                                                         | Testnet                                                                                          |
| ------------------ | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **`Network Name`** | _"IoTeX Mainnet"_                                                                               | _"IoTeX Testnet"_                                                                                |
| **`RPC URL`**      | See [Babel API Endpoints »](https://docs.iotex.io/reference/babel-web3-api#babel-api-endpoints) | See  [Babel API Endpoints »](https://docs.iotex.io/reference/babel-web3-api#babel-api-endpoints) |
| **`Chain ID`**     | 4689                                                                                            | 4690                                                                                             |
| **`Symbol`**       | IOTX                                                                                            | IOTX                                                                                             |
| **`Explorer URL`** | [https://iotexscan.io](https://iotexscan.io)                                                    | [https://testnet.iotexscan.io](https://testnet.iotexscan.io)                                     |

![](<../../.gitbook/assets/image (51).png>)

### 3. Save and select the IoTeX network

Click the **`Save`** button and make sure **IoTeX** is selected as the active network:

![](<../../.gitbook/assets/image (52).png>)

## Import your ioPay wallets to Metamask

If you have IoTeX accounts already set up in [ioPay](https://iopay.iotex.io), you can easily import them into Metamask by simply importing their private keys. Ses the sections below to learn how to access the private key in ioPay.

![Import an account in Metamask by private key](<../../.gitbook/assets/image (69).png>)

{% hint style="warning" %}
Please notice that Metamask will show your IoTeX wallet address in the **Web3** **format**, so you will see an address starting by`"0x.."`: as long as the private key is the same, that address represents the exact same blockchain account as in ioPay, they just use different formats for the public address representation. [Read more...](../basic-concepts/address-conversion.md)
{% endhint %}

### Access the private key in ioPay mobile

In ioPay mobile, you can display the private key by tapping the little icon in the top right of the screen:

![](<../../.gitbook/assets/image (70).png>)

### Access the private key in ioPay desktop

In ioPay Desktop, select "**Export Keystore**", then click "**Show Private Key**":

![](<../../.gitbook/assets/image (71).png>)
