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

## Fee Payments

The `payInvoiceERC20` function handles fee payments by transferring the specified fee amount to the provided fee address when the payment is due.

### payInvoiceERC20

Handles fee payments by transferring the specified fee amount to the provided fee address when the payment is due.

```solidity
function payInvoiceERC20(
    address _payee,
    address _feeAddress,
    uint40 _dueDate,
    uint256 _amount,
    uint256 _feeAmount,
    bytes calldata _paymentReference,
    bool _shouldPayoutViaRequestNetwork
) external nonReentrant whenNotPaused
```

### payOutERC20Invoice

Transfers the fee amount to the fee address when the payment is due.

```solidity
function payOutERC20Invoice(bytes[] calldata payoutReferencesArray) external nonReentrant
```

The `payInvoiceERC20` function ensures that the fee address is valid and that the total amount, including the fee, is transferred to the contract. The `payOutERC20Invoice` function handles the actual transfer of the fee to the fee address. The fee payments are managed through the `paymentMapping` and the `payOutERC20Invoice` function, ensuring that the fee is paid to the specified address when the payment is due.
