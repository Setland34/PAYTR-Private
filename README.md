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

## ERC20 Fee Proxy Functions

The `Paytr` contract includes functions for setting and getting the ERC20 fee proxy address.

### setERC20FeeProxy

Sets the ERC20 fee proxy address.

```solidity
function setERC20FeeProxy(address _ERC20FeeProxyAddress) external onlyOwner
```

### getERC20FeeProxy

Gets the ERC20 fee proxy address.

```solidity
function getERC20FeeProxy() external view returns (address)
```

This is my commit message

Signed-off-by: Random J Developer <random@developer.example.org>
