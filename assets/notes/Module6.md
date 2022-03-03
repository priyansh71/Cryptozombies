- After you deploy your contract, it gets a fixed address on Ethereum where it will live forever.
- The other thing Web3.js will need to talk to your contract is its ABI.
    ABI stands for Application Binary Interface. Basically it's a representation of your contracts' methods in JSON format that tells Web3.js how to format function calls in a way your contract will understand.
- ```call``` is used for view and pure functions. It only runs on the local node, and won't create a transaction on the blockchain.
- ```view``` and ```pure``` functions are read-only and don't change state on the blockchain. They also don't cost any gas, and the user won't be prompted to sign a transaction with MetaMask.
- ```send``` will create a transaction and change data on the blockchain. You'll need to use send for any functions that aren't view or pure.
- sending a transaction will require the user to pay gas, and will pop up their Metamask to prompt them to sign a transaction. When we use Metamask as our web3 provider, this all happens automatically when we call send().
- In Solidity, when you declare a variable public, it automatically creates a public "getter" function with the same name.
- sending a transaction requires a from address of who's calling the function (which becomes msg.sender in your Solidity code). We'll want this to be the user of our DApp, so MetaMask will pop up to prompt them to sign the transaction.
- ```receipt``` fires when the transaction is included into a block on Ethereum, which means our zombie has been created and saved on our contract
- In order to filter events and only listen for changes related to the current user, our Solidity contract would have to use the indexed keyword.
- We can even query past events using getPastEvents, and use the filters fromBlock and toBlock to give Solidity a time range for the event logs ("block" in this case referring to the Ethereum block number)

