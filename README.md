# MyToken

A simple Solidity smart contract for an ERC20-like token with minting and burning functionalities.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

MyToken is a basic smart contract written in Solidity that allows for the creation, minting, and burning of a custom token. The token has public variables to store details like the token name, abbreviation, and total supply, and supports balance management through mint and burn functions.

## Installation

To get started with the project, you need to have the following installed:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/)
- [Truffle](https://www.trufflesuite.com/truffle)
- [Ganache](https://www.trufflesuite.com/ganache) (for local development and testing)

### Steps

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/mytoken.git
    cd mytoken
    ```

2. Install dependencies:

    ```bash
    npm install
    ```

3. Compile the smart contract:

    ```bash
    truffle compile
    ```

4. Deploy the smart contract:

    ```bash
    truffle migrate
    ```

5. Run tests:

    ```bash
    truffle test
    ```

## Usage

Here is an example of how you can interact with the contract using Truffle console or any other web3 interface:

1. Open Truffle console:

    ```bash
    truffle console
    ```

2. Interact with the deployed contract:

    ```javascript
    let instance = await MyToken.deployed();
    
    // Minting tokens
    instance.mint("0xYourAddress", 1000);
    
    // Checking balance
    let balance = await instance.balances("0xYourAddress");
    console.log(balance.toString()); // Should output 1000

    // Burning tokens
    instance.burn("0xYourAddress", 500);
    
    // Checking balance again
    balance = await instance.balances("0xYourAddress");
    console.log(balance.toString()); // Should output 500
    ```

## Functions

### Public Variables

- `string public TokenName`: Stores the name of the token.
- `string public tokenAbbrv`: Stores the abbreviation of the token.
- `uint public totalSupply`: Stores the total supply of the token.

### Mapping

- `mapping(address => uint) public balances`: Maps addresses to their respective balances.

### mint

Mints new tokens and adds them to the specified address.

```solidity
function mint(address _address, uint _value) public
```

### burn

Burns tokens from the specified address if the balance is sufficient.

```solidity
function burn(address _address, uint _value) public
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/yourFeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/yourFeature`).
5. Open a pull request.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgements

- Thanks to the Ethereum and Solidity documentation for guidance.
- Inspired by various ERC20 token implementations.
