# MIAYOOO

First, we have some public variables declared:

string public tokenName = "TalgiaCoin";
string public tokenAbbrv = "TLC";
uint public totalSupply = 0;

These variables define the name, abbreviation, and total supply of the token. The public keyword means that these variables can be accessed and read by anyone who interacts with the contract.

Next, we have a mapping variable declared:

mapping(address => uint) public balances;

This mapping variable is used to keep track of the balance of each address that holds the token. The address type represents an Ethereum address, and the uint type represents an unsigned integer.

After that, we have two functions defined:

function mint (address _address, uint _value) public{
    totalSupply += _value;
    balances [_address] += _value;
}

function burn (address _address, uint _value) public{
    if (balances[_address] >=_value) {
        totalSupply -= _value;
        balances [_address] -= _value;
    }
}

The mint function is used to create new tokens and assign them to a particular address. It takes two parameters: _address, which is the address that will receive the newly-minted tokens, and _value, which is the number of tokens to be created. Inside the function, we increment the totalSupply variable by the value of _value, and we add the same amount to the balances mapping at the key _address.

The burn function is used to destroy existing tokens. It takes the same parameters as mint. However, before destroying any tokens, the function first checks if the address has enough tokens to burn by verifying that their balance is greater than or equal to _value. If this condition is met, we decrement the totalSupply variable by the value of _value, and we subtract the same amount from the balances mapping at the key _address

That's it! This contract allows anyone to create and destroy tokens on the Ethereum blockchain, and it keeps track of the balance of each address that holds the token.
