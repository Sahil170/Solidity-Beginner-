# TOKEN CONTRACT

This Solidity program is a contract that creates an Token and sent to users/addresses. This is my Metacrafters ETH Beginner Final Project
## Description

This program is a smart contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has 6 functions, i.e. Mint, Burn and 4 Getter functions. By using the mint function we can add more tokens to the total supply and send tokens to address and by using the burn function we can remove the tokens from total supply and also remove it from the address. I have also added a check measure where if the current balance of the user is less than the amount that is entered to be burned the transaction will fail

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ETH_Token.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity >=0.8.2 <0.9.0;

contract MyToken {

    // public variables here
    string public tokenName = "GetRekt";
    string public tokenAbbvr = "REKT";
    uint public totalSupply = 0;


    // mapping variable here
    mapping(address=>uint) public tokenHolders;


    // mint function
    function mint(address _address, uint _value) public{
        totalSupply+=_value;
        tokenHolders[_address] += _value;
    }


    // burn function
    function burn(address _address, uint _value) public{
        require(tokenHolders[_address] > _value, "Cannot burn more than balance tokens");
        totalSupply-=_value;
        tokenHolders[_address] -= _value;
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.2" (or another compatible version), and then click on the "Compile solidity.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the available functions. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "totalSupply" function to see the total supply of the token. Execute different functions and try out the contract.

## Authors

Sahil Aftab
