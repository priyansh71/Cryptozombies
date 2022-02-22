## zombie attack

- A mapping is essentially a key-value store for storing and looking up data.
- In Solidity, there are certain global variables that are available to all functions. One of these is msg.sender, which refers to the address of the person (or smart contract) who called the current function.
- Note: In Solidity, function execution always needs to start with an external caller. A contract will just sit on the blockchain doing nothing until someone calls one of its functions. So there will always be a msg.sender.
- Require makes it so that the function will throw an error and stop executing if some condition is not true.
- We use inheritance by using the ```is``` keyword.
- In Solidity, there are two locations you can store variables — in storage and in memory.

    - Storage refers to variables stored permanently on the blockchain. Memory variables are temporary, and are erased between external function calls to your contract. Think of it like your computer's hard disk vs RAM.
    - Most of the time you don't need to use these keywords because Solidity handles them by default. State variables (variables declared outside of functions) are by default storage and written permanently to the blockchain, while variables declared inside functions are memory and will disappear when the function call ends.
    - [Example](https://cryptozombies.io/en/lesson/2/chapter/7)
- In addition to public and private, Solidity has two more types of visibility for functions: internal and external. 
    - internal is the same as private, except that it's also accessible to contracts that inherit from this contract. (Hey, that sounds like what we want here!).
    - external is similar to public, except that these functions can ONLY be called outside the contract — they can't be called by other functions inside that contract. We'll talk about why you might want to use external vs public later.
- For our contract to talk to another contract on the blockchain that we don't own, first we need to define an interface.
- By including interfaces in our dapp's code our contract knows what the other contract's functions look like, how to call them, and what sort of response to expect.