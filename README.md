# TypeScript Solidity Boilerplate

## Hardhat Shorthand

```shell
npm i -g hardhat-shorthand
```

https://hardhat.org/guides/shorthand.html

### Common Shorthand Commands

-   `hh compile` - to compile smart contract and generate typechain ts bindings
-   `hh test` - to run tests
-   `hh deploy` - to deploy to local network (see options for more)
-   `hh node` - to run a localhost node
-   `hh help` - to see all available commands
-   `hh TABTAB` - to use autocomplete
-   `hh` - to see help and all task

## Usage

### Setup

#### 1. Install Dependencies

```shell
npm install
```

#### 2. Environment Setup

Create `.env` file and add your environment variables.

Make sure you include either `MNEMONIC` or `PRIVATE_KEY` in your `.env` file.

#### 3. Compile Contracts

```shell
npm run compile
```

### Example Flow - Deploy ERC721 Token

#### 1. Deploy BasicERC721 Contract

```shell
hh deploy --network mumbai --tags BasicERC721
```

#### 2. Verify Contract

```shell
hh --network mumbai etherscan-verify
```

#### 3. Interact With Contract - Mint

```shell
hh erc721-mint \
 --contract 0x... \
 --recipient 0x... \
 --network mumbai
```

---

### Testing

#### Run Tests

```shell
npm run test
```

#### Run Coverage

```shell
npm run coverage
```

---

### Project Hygiene

#### Prettier - Non Solidity Files

```shell
npm run format:check
npm run format:write
```

#### Lint - Non Solidity Files

```shell
npm run lint:check
npm run lint:fix
```

#### Prettier - Solidity

```shell
npm run sol:format:check
npm run sol:format:write
```

#### Solhint - Enforcing styles and security best practices

```shell
npm run solhint
```

## Project Structure

```text
.
├── contracts
│   ├── BasicERC1155.sol
│   ├── BasicERC20.sol
│   └── BasicERC721.sol
├── deploy
│   ├── Deploy_BasicERC1155.ts
│   ├── Deploy_BasicERC20.ts
│   └── Deploy_BasicERC721.ts
├── deployments
├── hardhat.config.ts
├── tasks
│   ├── erc1155
│   ├── erc20
│   ├── erc721
│   └── utils
└── test
    ├── BasicERC1155.ts
    ├── BasicERC20.ts
    └── BasicERC721.ts
```

## Supported Networks

-   Hardhat Network (localhost)
-   Ethereum Mainnet
-   Ethereum Sepolia Testnet
-   Polygon Mainnet
-   Polygon Mumbai Testnet

add more networks in `hardhat.config.ts` file.
