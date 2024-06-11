# ETH-PROOF-PROJECT-ASSESSMENT
TOTAL SUPPLY :
This Solidity code functions as a playground for generating and erasing tokens. This Solidity code provides a straightforward example of handling virtual tokens by demonstrating how to create and destroy tokens. It's similar to engaging with digital currency! We have the option to either distribute additional coins to our friends or remove coins from circulation if they are no longer needed.
DESCRIPTION :
This Solidity code demonstrates a basic token system that allows for the generation and deletion of digital tokens. Called "MYToken," it keeps track of both the total token supply and the balances of individual addresses. The MINT function creates fresh tokens and assigns them to a specified address, increasing the overall supply. On the other hand, the BURN feature removes tokens from a designated address, consequently decreasing the overall supply and the balance of that address. Users can easily simulate the issuance and depletion of tokens within this environment due to its simple functions.
GETTING STARTED :
REQUIREMENT : 
The code begins by establishing fundamental details about the token, such as its name, symbol, and initial amount of supply.
A list is used to keep track of the number of tokens each individual possesses.
There is a method to increase the number of tokens within the system, similar to how new money is printed and distributed to individuals.
Additionally, it is possible to eliminate tokens from the system by withdrawing them from circulation, however, this can only be done if the individual has a sufficient amount to relinquish.
It verifies that no one can withdraw more tokens than they possess, ensuring the security and fairness of the system.
RUNNING PROGRAM :
To execute this program, you have the option of using Remix, which is an online Solidity IDE. To begin, navigate to the Remix website found at https://remix.ethereum.org/.
When you reach the Remix website, make a new file by selecting the "+" symbol on the sidebar located on the left side of the page. Save the document with a .sol file type (for example, MYTOKEN). Paste the code provided below :

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
    string public tokenName = "LAKSHIT";
    string public tokenAbbrv = "LKM";
    uint public totalSupply =0;

    // mapping variable here
    mapping(address => uint) public balances;
      
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burnt (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
    }
}
}


In order to compile the code, you should select the "Solidity Compiler" tab located on the left-hand sidebar. Ensure that the "Compiler" setting is selected as "0.8.0" (or a compatible version) before clicking on the "Compile MYToken.sol" button.
After compiling the code, you have the option to deploy the contract by selecting the "Deploy & Run Transactions" tab from the sidebar on the left. Choose the "MYToken" contract from the drop-down list, and proceed by clicking on the "Deploy" button.
After the contract has been implemented, you have the ability to engage with it. Select the "MYToken" contract on the left sidebar, then view the token Abbrev, tokenName, and total supply by clicking on them. When you input the address and token value and click on mint, the mint function will be triggered, and the same applies for burn.
AUTHOR :
@LAKSHIT MALHOTRA
LICENSE
THIS IS UNDER MIT LICENSE
