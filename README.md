# Paytr protocol smart contracts

You can find all our smart contracts in this repository.
At the moment there's one main contact, `Paytr.sol`.

Looking to use the Paytr protocol for your project? Check out our documentation [here](https://paytr.gitbook.io/product-docs/).

## Forge test

All the tests are located in the test folder.
Install the necessary dependencies with `forge install`.

You will need to run the tests on a Sepolia fork by using this command:
`forge test --fork-url https://sepolia.infura.io/v3/YOURKEY` or
`forge test --fork-url https://eth-sepolia.g.alchemy.com/v2/YOURKEY`

## Frequently Asked Questions (FAQ)

### How do I install the Forge Standard Library?

To install the Forge Standard Library, you can use the `forge install` command. Here are the steps to follow:

* Open your terminal or command prompt.
* Navigate to the root directory of your project.
* Run the following command:
  ```bash
  forge install foundry-rs/forge-std
  ```
* This command will install the Forge Standard Library in your project, which includes helpful contracts and libraries for use with Forge and Foundry.

For more information, you can refer to the `lib/forge-std/README.md` file in the repository.

## Contributing Guidelines

We welcome contributions to the Paytr protocol! To contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes and commit them with clear and concise commit messages.
4. Push your changes to your forked repository.
5. Submit a pull request to the main repository.

### Code Style

* Follow the existing code style and conventions.
* Write clear and concise code with appropriate comments.
* Ensure your code is well-documented.

### Testing

* Write tests for your changes to ensure they work as expected.
* Run the tests locally to verify that they pass.
* Include any necessary test files in your pull request.

### Documentation

* Update the documentation to reflect your changes.
* Ensure that the documentation is clear and easy to understand.

## Usage Examples

### Creating an Invoice

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "Paytr.sol";

contract InvoiceExample {
    Paytr paytr;

    constructor(address _paytrAddress) {
        paytr = Paytr(_paytrAddress);
    }

    function createInvoice(address _payer, uint256 _amount) public {
        paytr.createInvoice(_payer, _amount);
    }
}
```

### Paying an Invoice

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "Paytr.sol";

contract PayInvoiceExample {
    Paytr paytr;

    constructor(address _paytrAddress) {
        paytr = Paytr(_paytrAddress);
    }

    function payInvoice(uint256 _invoiceId) public payable {
        paytr.payInvoice{value: msg.value}(_invoiceId);
    }
}
```

### Handling Fees

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "Paytr.sol";

contract FeeExample {
    Paytr paytr;

    constructor(address _paytrAddress) {
        paytr = Paytr(_paytrAddress);
    }

    function handleFee(uint256 _invoiceId) public {
        uint256 fee = paytr.calculateFee(_invoiceId);
        paytr.payFee{value: fee}(_invoiceId);
    }
}
```

### Managing Escrow Payments

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "Paytr.sol";

contract EscrowExample {
    Paytr paytr;

    constructor(address _paytrAddress) {
        paytr = Paytr(_paytrAddress);
    }

    function createEscrow(address _payer, address _payee, uint256 _amount) public {
        paytr.createEscrow(_payer, _payee, _amount);
    }

    function releaseEscrow(uint256 _escrowId) public {
        paytr.releaseEscrow(_escrowId);
    }
}
```
