## battle system

- Visibility modifiers that control when and where the function can be called from.
    - ```private``` means it's only callable from other functions inside the contract.
    - ```internal``` is like private but can also be called by contracts that inherit from this one. 
    - ```external``` can only be called outside the contract.
    - ```public``` can be called anywhere, both internally and externally.

- State modifiers, which tell us how the function interacts with the BlockChain.
    - ```view``` tells us that by running the function, no data will be saved/changed. 
    - ```pure``` tells us that not only does the function not save any data to the blockchain, but it also doesn't read any data from the blockchain.

Both of these don't cost any gas to call if they're called externally from outside the contract (but they do cost gas if called internally by another function).

- Custom modifiers, for these we can define custom logic to determine how they affect a function like:
    - [```onlyOwner```](https://github.com/priyansh71/cryptozombies/blob/b9ec77d929e83e90398a0af15d34b600489f0bfe/3.%20Advanced%20Solidity/ownable.sol#L35) 
    - [```aboveLevel```](https://github.com/priyansh71/cryptozombies/blob/b9ec77d929e83e90398a0af15d34b600489f0bfe/3.%20Advanced%20Solidity/zombiehelper.sol#L7)

- After you send Ether to a contract, it gets stored in the contract's Ethereum account, and it will be trapped there — unless you add a function to withdraw the Ether from the contract.
- It is important to note that you cannot transfer Ether to an address unless that address is of type address ```payable```. But the _owner variable is of type ```uint160```, meaning that we must explicitly cast it to address payable.
- Once you cast the address from uint160 to address payable, you can transfer Ether to that address using the transfer function, and ```address(this).balance``` will return the total balance stored on the contract.
- [Generating truly random numbers in solidity.](https://ethereum.stackexchange.com/questions/191/how-can-i-securely-generate-a-random-number-in-my-smart-contract)

