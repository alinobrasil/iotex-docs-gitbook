# Deploy a token in Remix IDE

The easiest way to deploy an XRC20 token on IoTeX is using Remix IDE in conjunction with Metamask. We will deploy the reference implementation from Openzeppelin of a [preset ERC20 token with fixed supply and burnable](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v4.2/contracts/token/ERC20/presets/ERC20PresetMinterPauser.sol).&#x20;

### Hints for first timers 👇

{% hint style="info" %}
**If this is your first smart contract deployment**, and you're not really sure where to start from, or if you maybe find some of the following concepts unclear, these are some useful links to official resources: \
\
1\) [**Intro to Ethereum Smart Contracts**](https://ethereum.org/en/developers/docs/smart-contracts/)\
2\) [**Intro to Smart Contracts Deployment**](https://ethereum.org/en/developers/docs/smart-contracts/deploying/) \
3\) [**Intro to Development Frameworks**](https://ethereum.org/en/developers/docs/frameworks/)
{% endhint %}

{% hint style="info" %}
Please note that in this section we'll make use of [**OpenZeppelin**](https://www.openzeppelin.com/defender), "a platform to develop, deploy and operate smart contract projects on Ethereum and every other EVM and eWASM-powered blockchain". OpenZeppelin also offers a whole set of community audited smart contracts. You can check out their **GitHub** repository [**here**](https://github.com/OpenZeppelin/openzeppelin-sdk).&#x20;
{% endhint %}

{% hint style="info" %}
Once **deployment is done**, you might want to think about registering your token and including it in the IoTeX Ecosystem tools such as the [block explorer](https://iotexscan.io) and the official [ioPay wallets](https://iotex.io/iopay). You can learn all about registering your token [**here**](register-your-token-in-the-ecosystem.md).&#x20;
{% endhint %}

## 1. Configure Metamask

Make sure you configured Metamask for use with the IoTeX Blockchain and that the IoTeX network, whether its mainnet or testnet, is actually selected in Metamask:

{% content-ref url="../wallets/metamask.md" %}
[metamask.md](../wallets/metamask.md)
{% endcontent-ref %}

## 2. The source code

We will deploy the token contract defined in the contract below, which is taken from the Openzeppelin preset [ERC20PresetFixedSupply.sol](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v4.2/contracts/token/ERC20/presets/ERC20PresetFixedSupply.sol) with a minor change to the import statement required to access the Openzeppelin files over the web and allow the compilation in a Web IDE:

```csharp
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "https://raw.githubusercontent.com/OpenZeppelin/openzeppelin-contracts/release-v4.2/contracts/token/ERC20/extensions/ERC20Burnable.sol";

/**
 * @dev {ERC20} token, including:
 *
 *  - Preminted initial supply
 *  - Ability for holders to burn (destroy) their tokens
 *  - No access control mechanism (for minting/pausing) and hence no governance
 *
 * This contract uses {ERC20Burnable} to include burn capabilities - head to
 * its documentation for details.
 *
 * _Available since v3.4._
 */
contract ERC20PresetFixedSupply is ERC20Burnable {
    /**
     * @dev Mints `initialSupply` amount of token and transfers them to `owner`.
     *
     * See {ERC20-constructor}.
     */
    constructor(
        string memory name,
        string memory symbol,
        uint256 initialSupply,
        address owner
    ) ERC20(name, symbol) {
        _mint(owner, initialSupply);
    }
}
```

## Open Remix IDE and paste the code

Open the [Remix IDE](https://remix.ethereum.org/) and create a new file under the `Contracts` folder: call it `Simpletoken.sol` and paste the source code of the token, then save the file:

![](<../../.gitbook/assets/image (73).png>)

## 3. Compile the contract

Move to the "_Solidity Compiler"_ tab in the left navigator, select the correct compiler version as required by the **`pragma`** directive in the contract, then compile:

![](<../../.gitbook/assets/image (74).png>)

## Deploy the contract

Switch to the "_Deploy & Run Transactions_" tab, select "_Injected Web3_" as the environment to make Remix use your Metamask account as a signer.

&#x20;Next to the "_Deploy_" button, you must fill in the required constructor arguments which are:

* **Token name**: "Simple Token"
* **Token symbol**: "SIM"
* **Total Supply** (in [Rau](../basic-concepts/iotx-token.md#iotx-fractions)): 1000000000000000000000000 (1 Million tokens)
* **Address**: the contract owner address, which will also receive the whole supply upon deployment

So this is how your Deploy arguments field should look like:

![](<../../.gitbook/assets/image (75).png>)

Finally, hit "_Deploy_" and confirm the deployment transaction in Metamask (make sure [you have some IOTX](../iotx-faucets/) to pay for gas in your Metamask wallet!&#x20;

## Interact with the Contract

Once the contract is deployed, you can easily interact with it directly in the Remix UI. For example, you can query the balance of the contract creator address, which should have received the entire total supply of the token upon deployment.

Look for the "_SimpleToken_" deployed contract in the left panel and expand it. Input the address you used to deploy the contract in the arguments field of the "`balanceOf`" function, click the "`balanceOf`" button to actually execute the contract call, and you should see the balance of SIM for your account right below the button:

![](<../../.gitbook/assets/image (61).png>)
