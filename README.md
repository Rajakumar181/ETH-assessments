MyToken Solidity Smart Contract

Simple Overview of Use/Purpose:
This Solidity smart contract defines a custom token called "DOLA" with the abbreviation "DLA". It includes functionalities for minting new tokens, burning existing tokens, and keeping track of token balances for different addresses.

Description:
The MyToken contract allows the creation and management of a simple ERC20-like token on the Ethereum blockchain. It features public variables to store token details, a mapping to track balances, and functions to mint and burn tokens. The contract is designed to increase and decrease the total supply of tokens dynamically while ensuring that tokens are only burned if the sender has a sufficient balance.

Getting Started:
Installing
Install Remix IDE or any other Solidity development environment.
Create a new file and copy the MyToken contract code into it.
How/Where to Download Your Program
The contract code can be directly copied from the provided snippet and pasted into your development environment.
Any Modifications Needed to Be Made to Files/Folders
No modifications are needed to the contract code for basic usage.
Executing Program:
How to Run the Program
Open Remix IDE and create a new file named MyToken.sol.
Paste the provided contract code into MyToken.sol.
Compile the contract using the Solidity compiler version 0.8.18.
Deploy the contract to a local blockchain (e.g., Remix VM) or a testnet (e.g., Ropsten, Rinkeby).
Step-by-Step Bullets
Open Remix IDE.
Create a new file: MyToken.sol.
Paste the contract code into MyToken.sol.
Select the appropriate compiler version (0.8.18).
Compile the contract.
Deploy the contract using the "Deploy & Run Transactions" tab.
Interact with the deployed contract using the available functions (mint and burn).
Code Blocks for Commands:
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables here
    string public tokenName = "DOLA";
    string public tokenAbbrv = "DLA";
    uint public totalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
Help:
Any Advice for Common Problems or Issues
Ensure you are using the correct Solidity compiler version (0.8.18).
When burning tokens, ensure the sender's balance is greater than or equal to the amount being burned to avoid a failed transaction.
Always test the contract on a local blockchain or testnet before deploying to the mainnet.
Command to Run if Program Contains Helper Info
No additional helper commands are required for this contract.
Authors:
Contributors names and contact info:

Raja Kumar: @rajapusaho@gmail.com

License:
This project is licensed under the MIT License - see the LICENSE.md file for details.
