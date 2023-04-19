# MY TOKEN

The main objective of this solidity program is to implement a token contract that enables users to mint and burn tokens. Additionally, the program allows for the tracking of balances associated with specific addresses, and employs conditional statements to ensure that certain processes are carried out only when feasible.

## Description

This program is a straightforward contract that utilizes a mapping data structure to maintain a record of the number of tokens owned by a given address. The program features two functions, one to create tokens and another to remove them. Overall, this program serves as a practical simulation, demonstrating the workings of minting and burning tokens.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {
// public variables here
    string public tokenName = "TalgiaCoin";
    string public tokenAbbrv = "TLC";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value;
        balances [_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >=_value) {
        totalSupply -= _value;
        balances [_address] -= _value;
    }
}
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile myToken.sol" button.

To deploy the contract, click on the "Deploy and Run Transactions" button. This will open a new window that allows you to deploy the contract. Do not forget to select the “MyToken” contract before deploying.

In the deployment window “Deployed Contracts”, set the parameters for the balance, mint, and burn functions. 
* To mint new tokens, input the address of the recipient and the number of tokens you want to mint and click transact. 
* To burn tokens, input the address of the recipient and the number of tokens you want to burn and click transact. 
* To see current balances of the address, input the address of the recipient and the number of tokens you want to mint and click call. You can also see the total supply by clicking the “totalSupply” button.

## Authors

NTCIAN Lester
<br>
[Discord: @Lestalgia](https://discordapp.com/users/Lestalgia#2215)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
