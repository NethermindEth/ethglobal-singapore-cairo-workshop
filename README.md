# Starknet Smart Contract Workshop

Welcome to the workshop on **Creating and Deploying Your First Smart Contract on Starknet (Sepolia Testnet)**! This guide will help you get started with Starknet, using tools like Cairo, Scarb, Starknet Foundry, and Starkli. By the end of this workshop, you will have successfully deployed your first smart contract on the Starknet Sepolia Testnet.

My Telegram handle: @ametel01

## Prerequisites

- Basic understanding of smart contracts
- Installed dependencies: Git, Bash

## Installation Instructions

### 1. Install `asdf` for Version Management

We'll use `asdf` to manage the versions of tools required for this workshop.

```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.1
```

### 2. Install Scarb

Scarb is the package manager for Cairo projects.

```bash
asdf plugin add scarb
asdf install scarb latest
```

### 3. Install Starknet Foundry

Starknet Foundry provides testing and compilation tools for Starknet.

```bash
asdf plugin add starknet-foundry
asdf install starknet-foundry latest
```

### 4. Install Starkli

Starkli is the command-line interface for Starknet account and contract interactions.

```bash
curl https://get.starkli.sh | sh
Starkliup
```

## Setting Up the Project

### 1. Initialize a New Package

Start by initializing a new Scarb package for your smart contract:

```bash
snforge init <package-name>
```

### 2. Compile Your Contract

Compile your Cairo smart contract:

```bash
Scarb build
```

### 3. Run Unit Tests

Run the tests to ensure everything works:

```bash
snforge test
```

## Preparing for Deployment

### 1. Create a `.env` File

Set the Starknet RPC endpoint to interact with the Sepolia Testnet. In the root directory of your project, create a `.env` file with the following content:

```bash
export STARKNET_RPC="https://starknet-sepolia.public.blastapi.io/rpc/v0_7"
```

### 2. Create a Signer

Create a new signer keystore for your account:

```bash
starkli signer keystore new keystore.json
```

Add this line to your `.env` file:

```bash
export STARKNET_KEYSTORE="keystore.json"
```

### 3. Initialize and Deploy Your Account

Initialize your account:

```bash
starkli account oz init account.json
```

Deploy your account:

```bash
starkli account deploy account.json
```

## Contract Deployment

### 1. Declare Your Contract

Before deploying, declare your contract on Starknet:

```bash
starkli declare <path-to-contract>
```

### 2. Deploy Your Contract

Once declared, deploy your contract by specifying the class hash:

```bash
starkli deploy <class-hash>
```

## Conclusion

Congratulations! You have successfully deployed your first Starknet smart contract. Feel free to explore further or modify the contract to test different functionalities.

## Troubleshooting

If you encounter any issues during the workshop, please refer to the official Starknet and Cairo documentation or ask for assistance.
