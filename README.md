# tokenToken
This Solidity program is a simple "tokenToken" application that explains the Solidity programming language's fundamental syntax and capabilities. The goal of this program aims to serve as the starting point for individuals who are new to Solidity and wish to learn how it works.

## Description
- 

## Getting Started
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
    string public tokenName = "TOKEN";
    string public tokenAbbrv = "TKN";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances [_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances [_address] >= _value) {
        totalSupply -= _value;
        balances [_address] -= _value;
        }
    }

}

## Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. 
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Then copy the code given in the assessment. 

## Author
       Carl Jasper M. Adrales
       8214773@ntc.edu.ph

## License
       This project is licensed under the MIT License - see the LICENSE file for details
