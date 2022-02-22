## zombie factory

- State variables are permanently stored in contract storage. This means they're written to the Ethereum blockchain. Think of them like writing to a DB.
- Well, there are two ways in which you can pass an argument to a Solidity function:

    - By value, which means that the Solidity compiler creates a new copy of the parameter's value and passes it to your function. This allows your function to modify the value without worrying that the value of the initial parameter gets changed.
    - By reference, which means that your function is called with a... reference to the original variable. Thus, if your function changes the value of the variable it receives, the value of the original variable gets changed.
- ```Note``` : It's convention (but not required) to start function parameter variable names with an underscore (_) in order to differentiate them from global variables. We'll use that convention throughout our tutorial.
- In Solidity, functions are public by default. This means anyone (or any other contract) can call your contract's function and execute its code. This can make your contract vulnerable to attacks. Thus it's good practice to mark your functions as private by default, and then only make public the functions you want to expose to the world.
- It's convention to start private function names with an underscore (_).
- **View** function, meaning it's only viewing the data but not modifying it.
    ```
    function sayHello() public view returns (string memory) {
    ```
- Solidity also contains **Pure** functions, which means you're not even accessing any data in the app. This function doesn't even read from the state of the app — its return value depends only on its function parameters.
    ```
    function _multiply (uint a, uint b) private pure returns (uint) {
        return a * b;
    }
    ```
- Ethereum has the hash function **keccak256** built in, which is a version of SHA3. A hash function basically maps an input into a random 256-bit hexadecimal number. A slight change in the input will cause a large change in the hash. Also important, **keccak256** expects a single parameter of type bytes.
- Events are a way for your contract to communicate that something happened on the blockchain to your app front-end, which can be 'listening' for certain events and take action when they happen.

