# Project Title

Creating a Token

## Description

This program provides the user with the ability to create a token consists of name ,abbreviation and total number and some added functionality :-<br />
1.mint() :- this function allows you to add amount to specific address.<br />
2.burn() :- this is opposite of mint() ,this function allows you to remove any amount from a specified address if the address contain enough amount to do so.<br />

This program aims to provide you with a basic token creating code with can be changed to creating something more creative and functional.

## Getting Started

### Installing

* To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

### Executing program


Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Token.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokkenName = "zoltrax";
    string public tokkenAbbrv = "ZOL";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint )public balances;

    // mint function
    function mint(address _add,uint _value)public {
        totalSupply += _value;
        balances[_add] += _value;
    }

    // burn function
    function burn(address _add,uint _value) public{
        if(balances[_add]>=_value){
            totalSupply -= _value;
            balances[_add] -= _value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint function or the burn function to provide some amount to any addresses of your liking.


## Authors

Udai Raj Singh Negi<br />
udai.negi135@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
