# Paytr protocol smart contracts

You can find all our smart contracts in this repository.
At the moment there's one main contact, `Paytr.sol`.

Looking to use the Paytr protocol for your project? Check out our documentation [here](https://paytr.gitbook.io/product-docs/).

## Table of Contents

- [Project Overview](#project-overview)
- [Usage Examples](#usage-examples)
- [Contributing](#contributing)
- [License](#license)
- [Troubleshooting](#troubleshooting)
- [Changelog](#changelog)
- [Installing the Forge Standard Library](#installing-the-forge-standard-library)
- [Running Tests on a Sepolia Fork](#running-tests-on-a-sepolia-fork)

## Project Overview

The Paytr protocol is a decentralized payment solution that allows users to create and pay invoices, handle fees, and manage escrow payments. It leverages the power of blockchain technology to provide a secure and transparent payment system.

## Usage Examples

### Creating an Invoice

```solidity
// Example code for creating an invoice
```

### Paying an Invoice

```solidity
// Example code for paying an invoice
```

### Handling Fees

```solidity
// Example code for handling fees
```

### Managing Escrow Payments

```solidity
// Example code for managing escrow payments
```

## Contributing

We welcome contributions to the Paytr protocol. To contribute, please follow these guidelines:

1. Fork the repository and create a new branch for your changes.
2. Make your changes and ensure that the code passes all tests.
3. Submit a pull request with a clear description of your changes.

For more information, please refer to our [contributing guidelines](CONTRIBUTING.md).

## License

The Paytr protocol is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Troubleshooting

If you encounter any issues while using the Paytr protocol, please refer to the following troubleshooting tips:

- Ensure that you have installed all dependencies correctly.
- Check the configuration settings in the `foundry.toml` file.
- Verify that you are using the correct fork URL for running tests.

## Changelog

### v1.0.0

- Initial release of the Paytr protocol.

## Installing the Forge Standard Library

To install the Forge Standard Library, you can use the `forge install` command. Here are the steps to follow:

1. Open your terminal or command prompt.
2. Navigate to the root directory of your project.
3. Run the following command:

```bash
forge install foundry-rs/forge-std
```

This command will install the Forge Standard Library in your project, which includes helpful contracts and libraries for use with Forge and Foundry.

For more information, you can refer to the `lib/forge-std/README.md` file in the repository.

## Running Tests on a Sepolia Fork

All the tests are located in the test folder.
Install the necessary dependencies with `forge install`.

You will need to run the tests on a Sepolia fork by using this command:

```bash
forge test --fork-url https://sepolia.infura.io/v3/YOURKEY
```

or

```bash
forge test --fork-url https://eth-sepolia.g.alchemy.com/v2/YOURKEY
```

Replace `YOURKEY` with your actual API key from Infura or Alchemy.
