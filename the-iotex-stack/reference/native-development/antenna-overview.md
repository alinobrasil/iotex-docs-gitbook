# Antenna SDK Overview

"**Antenna"** is the IoTeX native SDK, allowing you to directly interact with a local or remote IoTeX node using a gRPC connection, and is available for the most popular programming languages.  The difference between developing using **Antenna** or [Web3 SDK](../../web3-development/web3.js.md) is that Antenna wraps the full [gRPC Native API](../node-core-api-grpc.md) of the IoTeX protocol and uses the [native representation of IoTeX addresses](../../basic-concepts/address-conversion.md#iotex-address-format).&#x20;

While IoTeX fully supports the Ethereum API, allowing you to use Web3 tools for dApp development, the fact that IoTeX architecture is more complex than Ethereum's, makes Antenna the necessary choice when you want to make use of IoTeX unique features. For example, "Delegates," "Block Producers," "Staking Transactions," "Buckets," "Voting," etc., are concepts that find no correspondence in Ethereum. Therefore if you want to use these features in your dApp, you won't find them in, e.g., Web3js: in this case, you will have to use Antenna.

[The Example code](reference-code/create-an-account.md) section includes examples for each supported language.

### Supported Languages <a href="#supported-languages" id="supported-languages"></a>

**antenna-js (Javascript):** [**Installation**](antenna-installation/install-antenna-js.md) **|** [**GitHub**](https://github.com/iotexproject/iotex-antenna)

**antenna-java (java):** [**Installation**](antenna-installation/antenna-java.md) **|** [**GitHub**](https://github.com/iotexproject/iotex-antenna-java)

**antenna-go (go lang):** [**Installation**](antenna-installation/antenna-go.md) **|** [**GitHub**](https://github.com/iotexproject/iotex-antenna-go)

**antenna-swift (iOS):** [**Installation**](antenna-installation/antenna-swift.md) **|** [**GitHub**](https://github.com/iotexproject/iotex-antenna-swift)

**antenna-embedded (C):** [**Installation**](antenna-installation/antenna-embedded.md) **|** [**GitHub**](https://github.com/iotexproject/iotex-antenna-embedded)

### Features <a href="#features" id="features"></a>

**Crypto**\
This module provides crypto functions to generate public/private keys, sign transactions and data, and other cryptographic utility functions.

**RPC-Methods**\
This module allows calling any RPC-Method provided by an IoTeX Blockchain Gateway.

**Account**\
This Class provides functions to create and manage blockchain accounts.

**Action**\
This module allows to create and manage blockchain actions.

**Contract**\
This class allows interaction with contracts deployed on the IoTeX Blockchain, given the contract address and the ABI.

**XRC20**\
This module allows to send, receive and query wallets for XRC20 tokens deployed on the IoTeX Blockchain.
