
# NFT (Non-Fungible Token)

This repository contains the code for a NFT (Non-Fungible Token) contract and a script to mint NFTs using the contract.

## Requirement

- Node.js
- Hardhat
- OpenZeppelin Contracts
- Alchemy API key
- MetaMask wallet 
 

## Installation
1. Clone this repository to your local machine.
2. Navigate to the project directory and run npm install.
3. Create a .env file in the root of the project and add the following variables:

```bash
API_URL=<your API URL>
PRIVATE_KEY=<your private key>
PUBLIC_KEY=<your public key>
```
Replace `<your API URL>`, `<your private key>`, and `<your public key>` with your own values.

4. Run the command npx hardhat compile to compile the smart contract.

## Usage
### Deploy the Contract
To deploy the smart contract to the Goerli network, run the following command:
```bash
npx hardhat run --network Goerli scripts/deploy.js
```
### Mint NFTs
To mint a new NFT, run the following command:
```bash
node scripts/mint-nft.js <tokenURI>
```
Replace `<tokenURI>` with the URI for the token metadata, which can be a URL pointing to a JSON file stored on IPFS or another decentralized storage platform.

## Smart Contract
The smart contract is located in the `contracts/MyNFT.sol` file. It inherits from the `ERC721URIStorage`,`Counters` and `Ownable` contracts provided by the OpenZeppelin library.

The `MyNFT` contract has a single function called `mintNFT` that allows the contract owner to mint a new NFT. The function takes two arguments: the recipient's address and the token URI. It returns the ID of the newly minted token.

## Scripts
### Deploy Script
The `deploy.js` script deploys the `MyNFT` contract to the Goerli network. It uses the `@nomiclabs/hardhat-ethers` plugin to interact with the Ethereum network.

### Mint NFT Script
The `mint-nft.js` script mints a new NFT using the `MyNFT` contract. It uses the `web3.js` library to create and send the transaction to the Ethereum network.

The script takes one argument: the token URI for the new NFT. It signs the transaction using the private key specified in the `.env` file and sends it to the network using the sendSignedTransaction method provided by `web3.js` .

## Acknowledgements

 - [OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/)
 - [Hardhat](https://hardhat.org/)
 - [Alchemy](https://alchemy.com/)
  - [Metamask]( https://metamask.io/)
