# MyToken Smart Contract

## Overview

`MyToken` is a simple Ethereum smart contract written in Solidity that implements a basic token. This contract allows for the minting and burning of tokens and includes essential functions and mappings to manage token balances and supply.

## Features

1. **Public Variables**:
   - `tok_name`: The name of the token.
   - `tok_abb`: The abbreviation (symbol) of the token.
   - `total_supply`: The total supply of the token.

2. **Mapping**:
   - `balances`: Maps addresses to their respective token balances.

3. **Functions**:
   - `mint`: Mints new tokens, increasing the total supply and the balance of a specified address.
   - `burn`: Burns tokens, decreasing the total supply and the balance of a specified address, with a check to ensure sufficient balance.

## Requirements

1. The contract must have public variables that store the details about the coin (Token Name, Token Abbreviation, Total Supply).
2. The contract must have a mapping of addresses to balances.
3. The contract must have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the specified address by that amount.
4. The contract must have a burn function, which works opposite to the mint function. It will take an address and a value, deduct the value from the total supply, and from the balance of the specified address. The burn function must ensure the balance of the address is greater than or equal to the amount being burned.

## Contract Details

### Public Variables

```solidity
string public tok_name = "James";
string public tok_abb = "JAS";
uint public total_supply = 0;
```

- `tok_name`: The name of the token, set to "James".
- `tok_abb`: The abbreviation of the token, set to "JAS".
- `total_supply`: The total supply of tokens, initialized to 0.

### Mapping

```solidity
mapping(address => uint) public balances;
```

- `balances`: A mapping that keeps track of each address's token balance.

### Mint Function

```solidity
function mint(address add1, uint value1) public {
    total_supply += value1;
    balances[add1] += value1;
}
```

- **Parameters**: 
  - `add1`: The address to mint tokens to.
  - `value1`: The amount of tokens to mint.
- **Functionality**: Increases the total supply and the balance of the specified address.

### Burn Function

```solidity
function burn(address add1, uint value1) public {
    if (balances[add1] >= value1) {
        total_supply -= value1;
        balances[add1] -= value1;
    }
}
```

- **Parameters**: 
  - `add1`: The address to burn tokens from.
  - `value1`: The amount of tokens to burn.
- **Functionality**: Decreases the total supply and the balance of the specified address, ensuring the address has sufficient balance before burning.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
