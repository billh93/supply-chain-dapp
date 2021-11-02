# Supply Chain DApp
This is an example of how a Decentralized Application using the Ethereum blockchain can be implemented in a supply chain. A seller can add items to the inventory system that is stored in the blockchain. A buyer can purchase such items from the inventory system. It can even keep track when a seller marks an item as Shipped, and where a buyer can mark the item as received.

## UML Diagram

You will find the following UML diagrams inside the UML directory.

1. Activity Diagram
2. Sequence Diagram
3. State Diagram
4. Class Diagram

## Prerequisites

The project uses the following libraries and versions.
* *Truffle* | 4.1.14 (core: 4.1.14) | Smart contract development environment.
  
* *Solidity* | 0.4.24 (solc-js) | Object-oriented, high-level language for implementing smart contracts
* *Infura* | | Allow the developers to connect to Ethereum networks without to store the full Ethereum blockchain.
* *Node* | 14.17.6 | JavaScript runtime that allow to develop different type de applications
* *Web3.js* | 1.3.5 | Collection of libraries that allow you to interact with a local or remote ethereum node using HTTP, IPC or WebSocket.
* *truffle-hdwallet-provider* | 1.0.17 | HD Wallet-enabled Web3 provider. Use it to sign transactions for addresses derived from a 12 or 24 word mnemonic.
* *MetaMask* | 10.3.0 | Crypto wallet & gateway to blockchain apps. Browser based.
* *Ownable* |  | Contract module which provides a basic access control mechanism, where there is an account (an owner) that can be granted exclusive access to specific functions.
* *Roles* |  | Library for implementing role-based access control.

## Transactions and Contracts

The project was deployed in the Rinkeby Network with the next transactions and contract addresses:

| Contract | Transaction | Address |
|---|---|---|
|  *Migrations* | [0xcb983e53406086d2096249ba31eeb873a1a52b622c8f57a1bcbf96c8d1da1e87](https://rinkeby.etherscan.io/tx/0xcb983e53406086d2096249ba31eeb873a1a52b622c8f57a1bcbf96c8d1da1e87) | [0x419f9fc753588052fdc7f6bec8c256d36f861a50](https://rinkeby.etherscan.io/address/0x419f9fc753588052fdc7f6bec8c256d36f861a50) |
|  *FarmerRole* | [0x6eedc6fe3f01057174d05d2c64a925b302db578345ec9b629d0c5f77a1664fed](https://rinkeby.etherscan.io/tx/0x6eedc6fe3f01057174d05d2c64a925b302db578345ec9b629d0c5f77a1664fed) | [0x5eb9f81de037522252fc1eb7e46e05b8815d63da](https://rinkeby.etherscan.io/address/0x5eb9f81de037522252fc1eb7e46e05b8815d63da) |
|  *DistributorRole* | [0xf1a31a6909a335157dcf348b4e9f4a207e42a17b0f71327679b1fac5c03be61b](https://rinkeby.etherscan.io/tx/0xf1a31a6909a335157dcf348b4e9f4a207e42a17b0f71327679b1fac5c03be61b) | [0x4a4bd58c26a0b3075235976f31ae5a07223698db](https://rinkeby.etherscan.io/address/0x4a4bd58c26a0b3075235976f31ae5a07223698db) |
|  *RetailerRole* | [0xbce31744ce5b8fcd53fa3049a5b89d62651bb425a59fdb30d7f96df4696ac798](https://rinkeby.etherscan.io/tx/0xbce31744ce5b8fcd53fa3049a5b89d62651bb425a59fdb30d7f96df4696ac798) | [0xdfa00c35aa73d0dbff6d811645ddf50813a28ee8](https://rinkeby.etherscan.io/address/0xdfa00c35aa73d0dbff6d811645ddf50813a28ee8) |
|  *ConsumerRole* | [0xbe9e499ca7d0f56c834011a472618e5398b19a57d099463d8839cccecb92b147](https://rinkeby.etherscan.io/tx/0xbe9e499ca7d0f56c834011a472618e5398b19a57d099463d8839cccecb92b147) | [0xe278a04f5cef450dec2f02278b4f445cb7ebbdf1](https://rinkeby.etherscan.io/address/0xe278a04f5cef450dec2f02278b4f445cb7ebbdf1) |
|  *SupplyChain* | [0x6c8f859a6501c72f3dc92843c3cf8b33889d833fed5cdf6146c3abe4ca244800](https://rinkeby.etherscan.io/tx/0x6c8f859a6501c72f3dc92843c3cf8b33889d833fed5cdf6146c3abe4ca244800) | [0xe664911a128a5fa865b4cd5e0d6aacdc9577a8ea](https://rinkeby.etherscan.io/address/0xe664911a128a5fa865b4cd5e0d6aacdc9577a8ea) |

## Run the application

1. **Node and NPM** installed - NPM is distributed with [Node.js](https://www.npmjs.com/get-npm)
```bash
# Check Node version
node -v
# Check NPM version
npm -v
```

2. **Truffle v4.1.14** - A development framework for Ethereum. 
```bash
# Unsinstall any previous version
npm uninstall -g truffle
# Install this specific Truffle version
npm install -g truffle@4.1.14
# Verify the version
truffle version
```

3. **Dependencies**
```bash
# Project's root directory
npm install
```

4. **MetaMask** - Install MetaMask extension in your browser.

5. **Ganache** - Install Ganache. This tool must be running to be able to test the DApp. Depending if you are using the desktop app or the command line version, the network url is different and we must configure it in Metamask and in this DApp.

6. **Add an account to Metamask** Choose one of the accounts that Ganache is showing and add it to Metamask with its private key. MetaMask must show the balance of the account.

7. **Compile the contracts**. Run in the terminal:
```bash
# Project's root directory.
truffle compile
```

8. **Migrate the contracts**. Run in the terminal:
```bash
# Project's root directory.
truffle migrate
```

9.  **(Optional) Test the contracts**. Run in the terminal:
```bash
# Project's root directory.
truffle test
```

10.  **Update Web3 Http provider**. Go to src/app.js:
```js script
// Go to line 77:
App.web3Provider = new Web3.providers.HttpProvider('<URL>');
// Replace it with the correct URL depending of Ganache version you are using.
// Desktop version
App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
// Or Command line version
App.web3Provider = new Web3.providers.HttpProvider('http://localhost:8545');
```

11. **Run the app**. Run in the terminal:
```bash
# Project's root directory.
npm run dev
```

## Deploying to Rinkeby

If you want to deploy the contracts to the Rinkeby network you must insert the following variables in the truffle-config.js file.
```bash
const infuraKey = "Your Infura Key";
const mnemonic = "Your Wallet 12 Secret Words";
```

Then you must run the next commands in terminal:
```bash
truffle compile
truffle migrate --network rinkeby --reset
```

