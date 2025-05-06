# Soroban Token Contract

This project is a standard token contract developed on the Soroban platform. Soroban is a smart contract platform that runs on the Stellar blockchain.
- Ergin TIRAVOGLU

# Project Image
![Project Illustration](ChatGPT%20Image%2020%20Nis%202025%2003_18_54.png)

# Project Overview

Soroban Token Contract is a comprehensive smart contract offering basic token functionalities. With this contract, you can perform standard token operations such as creating, transferring, burning tokens, and authorizing third-party spending.

# Features

- **Token Management**: Mint, burn, and transfer operations
- **Authorization**: Allowance mechanism for third-party spending
- **Admin Control**: Setting admin and operations requiring administrator permission
- **Metadata**: Token name, symbol, and decimal information
- **Account Freezing**: Freeze and unfreeze accounts to restrict token transfers

# Contract Structure

The project consists of the following modules:

- **admin**: Administrator functions and authorization
- **allowance**: Token spending permission management
- **balance**: Balance management operations
- **contract**: Main contract implementation and token interface
- **metadata**: Token metadata (name, symbol, decimals)
- **storage_types**: Storage data structures

# Technical Details

The contract is written in Rust programming language and compiled without standard library dependencies using the `#![no_std]` directive. This approach ensures that the contract is smaller in size and operates more efficiently.

# Key Functions

## Token Management

- **mint**: Create new tokens (admin only)
- **burn**: Burn tokens
- **transfer**: Transfer tokens
- **balance**: View address balance

## Allowance Management

- **approve**: Grant spending permission to another address
- **allowance**: View granted permission amount
- **transfer_from**: Transfer tokens with permission
- **burn_from**: Burn tokens with permission

## Admin Operations

- **initialize**: Initialize the contract
- **set_admin**: Change the administrator address
- **freeze_account**: Freeze an account to restrict token transfers
- **unfreeze_account**: Unfreeze an account to allow token transfers

# Project Details:
The Soroban Token Contract is a blockchain-based smart contract built on the Soroban platform, operating on the Stellar blockchain. It provides a robust token management system, enabling users to mint, transfer, and burn tokens securely. Key features include account freezing, which allows administrators to restrict token transfers for specific accounts, and an allowance mechanism for third-party spending permissions. The contract also supports metadata storage for token details like name, symbol, and decimals.

# Vision

Our vision is to create a secure, flexible, and efficient token management solution for blockchain applications. By leveraging the Soroban platform, we aim to provide developers and users with a reliable framework for managing digital assets while ensuring transparency and control.

# Personal Story

This project was developed as part of my journey to explore blockchain technology and smart contract development. I wanted to create a secure and efficient token management system that could be used in real-world applications. Through this project, I gained hands-on experience with the Soroban platform, Stellar blockchain, and Rust programming. It has been a rewarding experience to build and refine this contract, and I hope it serves as a valuable resource for others in the blockchain community.

# Software Development Plan

### 1. Smart Contract Development
- **Functions**:
  - Implement core token functions: `mint`, `burn`, `transfer`, `balance`.
  - Add administrative functions: `initialize`, `set_admin`, `freeze_account`, `unfreeze_account`.
  - Include helper functions: `is_frozen` to check account status.
  - Implement allowance functions: `approve`, `allowance`, `transfer_from`, `burn_from`.
- **Variables**:
  - Use persistent storage (`Map`) for frozen accounts.
  - Store metadata for token details (name, symbol, decimals).
- **Features**:
  - Secure administrative controls for freezing/unfreezing accounts and minting tokens.
  - Allowance mechanism for third-party spending.
  - Ensure `transfer` function checks frozen account status.

### 2. Testing and Validation
- Write unit tests for all functions, including edge cases (e.g., frozen accounts, insufficient balance).
- Validate `transfer` function to reject transfers from frozen accounts.
- Test administrative functions like `set_admin`, `initialize`, and freezing/unfreezing accounts.

### 3. Front-End Development (Optional)
- Build a simple web interface for interacting with the contract.
  - Features: Mint tokens, transfer tokens, freeze/unfreeze accounts, view balances.
- Use JavaScript/TypeScript with a framework like React or Vue.js.
- Integrate with Stellar testnet using Soroban SDK.

### 4. Documentation
- Update `README.md` with:
  - Project description.
  - Instructions for deploying and interacting with the contract.
  - Details of smart contract functions and usage.
  - Add examples for freezing/unfreezing accounts and transferring tokens.

### 5. Deployment
- Deploy the smart contract to Stellar testnet.
- Verify deployment and test using Stellar testnet tools.
- Provide the contract address in `README.md` for reference.

# Contact

For questions or contributions, please open an issue or submit a pull request.



# Build

stellar contract build

- ℹ️ CARGO_BUILD_RUSTFLAGS=--remap-path-prefix=C:\Users\Ergin\.cargo\registry\src= cargo rustc --manifest-path=Cargo.toml --crate-type=cdylib --target=wasm32-unknown-unknown --release
   Compiling soroban-token-contract v0.0.6 (C:\Users\Ergin\Downloads\soroban-token-contract-master\soroban-token-contract-master)
    Finished `release` profile [optimized] target(s) in 2.95s
- ℹ️ Build Summary:
  - Wasm File: target\wasm32-unknown-unknown\release\soroban_token_contract.wasm
  - Wasm Hash: 23e2948fd9cd46f6f2361638d03a910a510af8873815f61d5ca7c75303882b9d
  - Exported Functions: 16 found
    - _
    - allowance
    - approve
    - balance
    - burn
    - burn_from
    - decimals
    - freeze_account
    - initialize
    - mint
    - name
    - set_admin
    - symbol
    - transfer
    - transfer_from
    - unfreeze_account
- ✅ Build Complete

# Contract Address

stellar keys address alice

GA3G5AX52W46Z6PJYKQZ6GMPSHC6UDAKMMXKW4ZM3CZJYVYY22LC62PT

# Deploy

stellar contract deploy --wasm target/wasm32-unknown-unknown/release/soroban_token_contract.wasm --source alice --network testnet --alias token_contract

- ℹ️ Simulating install transaction…
- ℹ️ Signing transaction: 2a63512db45ee731e5eed4e4a1264d6fc56c5bd0959c0463c7a1a42f4b5688a9
- 🌎 Submitting install transaction…
- ℹ️ Using wasm hash d680ae028cfe81641bc0f43bb6c328a9abb64fee2ba67ef525e87bdab2fdb8f5
- ℹ️ Simulating deploy transaction…
- ℹ️ Transaction hash is cd8f21a19f96a0412058209af2953e7f3151ac7c92ddc37de66f253fcb166864
- 🔗 https://stellar.expert/explorer/testnet/tx/cd8f21a19f96a0412058209af2953e7f3151ac7c92ddc37de66f253fcb166864
- ℹ️ Signing transaction: cd8f21a19f96a0412058209af2953e7f3151ac7c92ddc37de66f253fcb166864
- 🌎 Submitting deploy transaction…
- 🔗 https://stellar.expert/explorer/testnet/contract/CAT4HLXQDFI5OGDBQHL25KZ4VCXSODGM37CFFEYNW2SH7PR7X2ZE7B53
- ✅ Deployed!
- CAT4HLXQDFI5OGDBQHL25KZ4VCXSODGM37CFFEYNW2SH7PR7X2ZE7B53

Refactored

- ℹ️ Simulating install transaction…
- ℹ️ Signing transaction: 350743615c1019c8f2ed0a3c5fd4216df4fa886e9b78cf7b07f6647d9f4ebe34
- 🌎 Submitting install transaction…
- ℹ️ Using wasm hash 23e2948fd9cd46f6f2361638d03a910a510af8873815f61d5ca7c75303882b9d
- ℹ️ Simulating deploy transaction…
- ℹ️ Transaction hash is e477f302f94655ea71eb82a1c2c4000f49a6ae484dfbc958599a3308851f3f13
- 🔗 https://stellar.expert/explorer/testnet/tx/e477f302f94655ea71eb82a1c2c4000f49a6ae484dfbc958599a3308851f3f13
- ℹ️ Signing transaction: e477f302f94655ea71eb82a1c2c4000f49a6ae484dfbc958599a3308851f3f13
- 🌎 Submitting deploy transaction…
--🔗 https://stellar.expert/explorer/testnet/contract/CDC4FWQYOZCHHRRKW7HKTIYZU53HZDNTDKFFRC65MMQXQB6OQGAF24O7
- ✅ Deployed!
- ⚠️ Overwriting existing contract id: CAT4HLXQDFI5OGDBQHL25KZ4VCXSODGM37CFFEYNW2SH7PR7X2ZE7B53
- CDC4FWQYOZCHHRRKW7HKTIYZU53HZDNTDKFFRC65MMQXQB6OQGAF24O7



