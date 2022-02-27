## advanced solidity

- After you deploy a contract to Ethereum, it’s immutable, which means that it can never be modified or updated again. If there's a flaw in your contract code, there's no way for you to patch it later. You would have to tell your users to start using a different smart contract address that has the fix.
- There are cases when we want some part of the contract to be updated after it has been deployed on the blockchain, but don't want anyone else to edit it. One common practice that has emerged is to make contracts Ownable — meaning they have an owner (you) who has special privileges.
- ```constructor()``` is a constructor, which is an optional special function that has the same name as the contract. It will get executed only one time, when the contract is first created.
- Modifiers are kind of half-functions that are used to modify other functions, usually to check some requirements prior to execution. 
- What is [address(0)](https://ethereum.stackexchange.com/questions/23224/what-address0-stands-for)?
- ```_;``` is used to go call the fucntion if the modifier checking is successfully finished.
- In Solidity, your users have to pay every time they execute a function on your DApp using a currency called gas. Users buy gas with Ether (the currency on Ethereum), so your users have to spend ETH in order to execute functions on your DApp.
- You'll also want to cluster identical data types together in a ```struct``` so that Solidity can minimize the required storage space.
- An important security practice is to examine all your public and external functions, and try to think of ways users might abuse them. 
- ```Note``` : **calldata** is somehow similar to **memory**, but it's only available to external functions.
- ```view``` functions don't cost any gas when they're called externally by a user.
    This is because they don't actually change anything on the blockchain – they only read the data. So marking a function with view tells web3.js that it only needs to query your local Ethereum node to run the function, and it doesn't actually have to create a transaction on the blockchain (which would need to be run on every single node, and cost gas).
- ```Note``` : If a view function is called internally from another function in the same contract that is not a view function, it will still cost gas. This is because the other function creates a transaction on Ethereum, and will still need to be verified from every node. So view functions are only free when they're called externally.
- One of the more expensive operations in Solidity is using storage — particularly writes.
This is because every time you write or change a piece of data, it’s written permanently to the blockchain. Forever! Thousands of nodes across the world need to store that data on their hard drives, and this amount of data keeps growing over time as the blockchain grows. So there's a cost to doing that.
- [Consequences of using loops.](https://cryptozombies.io/en/lesson/3/chapter/12)