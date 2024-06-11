Project Title 

Simple Contract

Description

This project have public variables that store the details about coin (Token Name, Token Abbrv., Total Supply)
A mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
A burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.

Getting Started

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myTokens.sol). Copy and paste the following code into the file:

Executing program


    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.26;
    contract MyToken {

    // public variables here
    string public token_Name = "MetaCoin";
    string public token_Abbrv = "MTC";
    uint public Total_Supply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
     Total_Supply += _value;
     balances[_address] += _value; 
    }
    // burn function
    function burn (address _address, uint _value) public {
    if(balances[_address]>=_value){ 
    Total_Supply -= _value;
     balances[_address] -= _value;
     }   
    }
    }


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile myTokens.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myTokens" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with by using mint function to mint a value at a particular address,then you can verify the transaction by calling balances or total supply.You can also use burn function to burn tokens at a particular address.

Authors

Manjot Singh
