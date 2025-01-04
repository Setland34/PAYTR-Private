# Paytr protocol smart contracts

You can find all our smart contracts in this repository.
At the moment there's one main contact, `Paytr.sol`.

Looking to use the Paytr protocol for your project? Check out our documentation [here](https://paytr.gitbook.io/product-docs/).

## Install Forge Standard Library

To install the Forge Standard Library, you can use the `forge install` command. Here are the steps to follow:

* Open your terminal or command prompt.
* Navigate to the root directory of your project.
* Run the following command:
  ```bash
  forge install foundry-rs/forge-std
  ```
* This command will install the Forge Standard Library in your project, which includes helpful contracts and libraries for use with Forge and Foundry.

For more information, you can refer to the `lib/forge-std/README.md` file in the repository.

## Forge test

All the tests are located in the test folder.
Install the necessary dependencies with `forge install`.

You will need to run the tests on a Sepolia fork by using this command:
`forge test --fork-url https://sepolia.infura.io/v3/YOURKEY` or
`forge test --fork-url https://eth-sepolia.g.alchemy.com/v2/YOURKEY`
