# Counter Smart Contract - Foundry Project

A simple counter smart contract built with Foundry framework, featuring basic increment and set number functionality.

## 📋 Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Testing](#testing)
- [Deployment](#deployment)
- [Contract Functions](#contract-functions)

## 🎯 Overview

This project demonstrates a basic counter smart contract with the following features:
- Increment the counter value
- Set the counter to a specific value
- View the current counter value

The contract is built using Foundry, a fast Ethereum development toolkit.

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:
- Git
- A Unix-like shell (WSL on Windows, macOS, or Linux)
- Node.js (optional, for additional tooling)

## 📦 Installation

### 1. Install Foundry

First, install Foundry using the official installer:

```bash
curl -L https://foundry.paradigm.xyz | bash
```

### 2. Update Foundry

After installation, update Foundry to the latest version:

```bash
foundryup
```

### 3. Clone and Setup Project

```bash
# Clone the repository (if not already done)
git clone <your-repo-url>
cd FoundaryDeploymentCfx

# Initialize the Counter project
forge init Counter
cd Counter
```

## 📁 Project Structure

```
Counter/
├── src/
│   └── Counter.sol          # Main smart contract
├── script/
│   └── Counter.s.sol        # Deployment script
├── test/
│   └── Counter.t.sol        # Test files
├── foundry.toml             # Foundry configuration
└── lib/                     # Dependencies
```

## 🚀 Usage

### Building the Project

Compile your smart contracts:

```bash
forge build
```

### Running Tests

Execute the test suite:

```bash
forge test
```

For verbose output:

```bash
forge test -vv
```

## 🧪 Testing

The project includes comprehensive tests for the Counter contract:

- **test_Increment()**: Tests the increment functionality
- **testFuzz_SetNumber()**: Fuzz testing for the setNumber function

Run tests with:

```bash
forge test
```

## 🚀 Deployment

### Local Development

1. Start a local Anvil instance:

```bash
anvil
```

2. Deploy to local network:

```bash
forge script script/Counter.s.sol --rpc-url http://localhost:8545 --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80 --broadcast
```

### Conflux Testnet Deployment

1. Set your private key as an environment variable:

```bash
export PRIVATE_KEY="your_private_key_here"
```

2. Deploy to Conflux testnet:

```bash
forge script script/Counter.s.sol --rpc-url https://evmtestnet.confluxrpc.com --private-key $PRIVATE_KEY --broadcast -g 200
```

### Mainnet Deployment

For mainnet deployment, use the appropriate RPC URL and ensure you have sufficient funds:

```bash
forge script script/Counter.s.sol --rpc-url https://evm.confluxrpc.com --private-key $PRIVATE_KEY --broadcast -g 200
```

## 📜 Contract Functions

### Counter Contract

The `Counter` contract provides the following functions:

- **`number()`**: View function that returns the current counter value
- **`setNumber(uint256 newNumber)`**: Sets the counter to a specific value
- **`increment()`**: Increments the counter by 1

### Example Usage

```solidity
// Set the counter to 10
counter.setNumber(10);

// Increment the counter
counter.increment(); // Now the value is 11

// Get the current value
uint256 currentValue = counter.number();
```

## 🔧 Configuration

The project uses the default Foundry configuration in `foundry.toml`:

```toml
[profile.default]
src = "src"
out = "out"
libs = ["lib"]
```

## 📚 Additional Resources

- [Foundry Book](https://book.getfoundry.sh/)
- [Solidity Documentation](https://docs.soliditylang.org/)
- [Conflux Documentation](https://docs.confluxnetwork.org/)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is licensed under the UNLICENSED license.

## ⚠️ Security

- Never commit private keys or sensitive information
- Always test contracts thoroughly before deployment
- Use appropriate gas limits for your deployment network
- Consider using a multisig wallet for mainnet deployments

---

**Note**: This is a basic example project. For production use, ensure proper security audits and testing procedures are followed.