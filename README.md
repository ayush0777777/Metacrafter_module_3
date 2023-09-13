# Metacrafter_module_3

This is a simple solidity smart contract based on ERC20 by OpenZeppelin. 



# Description

It imports the erc20 contract and utilizes the burn mint and transfer functions of that contract by using custom functions.


### Executing program


You can paste this code into Remix IDE and compile and deploy this contract.

```javascript// SPDX-License-Identifier: MIT
pragma solidity ^0.8.9;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Ayush is ERC20, ERC20Burnable, Ownable {
    constructor() ERC20("Ayush", "ggwp") {
    }

    function customMint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
    function customBurnTokens(uint amount) public {
        _burn(msg.sender, amount);
    }
    function customTransferTokens(address to, uint256 amount) public {
        _transfer(msg.sender,to,amount);
    }
}
```


## Authors

  
Ayush Kumar


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
