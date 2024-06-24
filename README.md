# Simple Token Smart Contract

This Solidity program demonstrates the creation of a basic token using a smart contract. The aim is to understand the Solidity programming language syntax and to gain practical experience with token transactions.

## Overview

This program is a basic smart contract written in Solidity, designed for the Ethereum blockchain.

The contract includes token information, tracks balances of token holders, and provides functions to mint and burn tokens.

### Token Details

Below is the snippet that defines the token's name, abbreviation, and total supply.

```solidity
string public name = "META";
string public symbol = "MTA";
uint public totalSupply = 0;
```

### Balances Mapping

The following code keeps track of the token balances for different addresses.

```solidity
mapping(address => uint) public balances;
```

### Mint and Burn Functions

The `mint` function creates new tokens, increasing both the total supply and the balance of the specified address.

```solidity
function mint(address _to, uint _amount) public {
    totalSupply += _amount;
    balances[_to] += _amount;
}
```

The `burn` function destroys tokens, reducing both the total supply and the balance of the specified address.

```solidity
function burn(address _from, uint _amount) public {
    require(balances[_from] >= _amount, "Insufficient balance to burn");
    totalSupply -= _amount;
    balances[_from] -= _amount;
}
```

## Running the Contract

To execute this contract, you can use Remix, an online Solidity IDE. Visit [Remix](https://remix.ethereum.org/) to get started.

1. **Create a New File:** Click on the "+" icon in the left sidebar, name the file with a .sol extension (e.g., Token.sol).

2. **Write or Paste Code:** Open the new file and write your code, or copy the code provided above.

3. **Compile the Code:**
   - Go to the "Solidity Compiler" tab in the left sidebar.
   - Ensure the "Compiler" version is set to "0.8.4" (or another compatible version).
   - Click the "Compile Token.sol" button.

4. **Deploy the Contract:**
   - Open the "Deploy & Run Transactions" tab in the left sidebar.
   - Select the "Token" contract from the dropdown menu.
   - Click the "Deploy" button.

5. **Interact with the Contract:**
   - After deployment, you can call the `mint` and `burn` functions.
   - Enter the required parameters for each function and click the respective button.
   - View the transaction details in the bottom-right console and verify changes to the contract's state variables.

By following these steps, you can effectively interact with your smart contract and observe the token transactions.
