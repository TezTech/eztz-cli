# eztz-cli #
eztz-cli is a simple Node.js CLI (command-line interface) that provides similar functionality to the tezos-client, but without the need to run a full node. eztz-cli is being built to match functionality to the official tezos-client CLI, connecting to the Tezos blockchain via the RPC layer of a tezos-node (by default https://tezrpc.me/api is used).

Being a npm plugin, eztz-cli has the benefit of being extremely portable, lightweight and very developer friendly. eztz-cli is powered by the eztz.js library.

## Why?
The official tezos-client currently requires a full working node, and can be cumbersome to install, run and maintain for non-techy users. eztz-cli is extremely portable and works on all platforms, with the aim to contain the complete functionality of the tezos-client. No need to run and maintain a node, just install and get working on the Tezos blockchain now.

## Installation ##
You will need to ensure you have Node.js installed.

```
npm i -g eztz-cli
```

## Getting Started ##
* First we need to setup or identity:
```
eztz newIdentity main
eztz balance main
```
* No tez? No worries, time to create a free account (on the alphanet, free accounts start with 100k tez!)
```
eztz freeAccount main account1
eztz balance account1
```
* That's better, time to do a transfer!
```
eztz transfer 50000 account1 main
eztz balance account1
eztz balance main
```

Well done, you've created an identity, checked your balance several times, created a free account and made a transfer! All on the Tezos blockchain!

## Documentation
#### eztz man / eztz help
Currently not implemented - sorry! (not very helpful...)

#### eztz clearData
Clears the ~/.eztz.config.json file, removing all identities, contracts etc.
Note: This will delete all private keys

#### eztz newIdentity $label
Generates a new crypto identity, stored with the label $label.

#### eztz newAccount $id $label $amount
Generates a account (codeless contract) for $id, stored with the label $label and sent $amount from $id as a starting balance.
Note: Need to implement $spendable, $delegatable, $delegate and $fee variables

#### eztz freeAccount $id $label
Generates a new faucet/free account for $id, stored with the label $label.

#### eztz newContract $id $label $amount $code $initial
Originates a new contract for $id, stored with the label $label and sent $amount as a starting balance, $code as the code for the smart contract, with the storage being set to $initial.
Note: Need to implement $spendable, $delegatable, $delegate and $fee variables

#### eztz listIdentities
List all known identities (generated keys)

#### eztz listAccounts
List all know accounts (originated contracts without code, e.g. faucet/free accounts)

#### eztz listContracts
Lists all known contracts (originated contracts with code)

#### eztz balance $for
Returns the balance for $for (can be a label or a key of a contract, account or identity, or any valid key)

#### eztz setDelegate $for $delegate
Sets the delegate for $for (can be a label or a key of a contract or account) to the specified $delehate (can be label or any valid tz1 key)

#### eztz transfer $amount $from $to
Tramsfers $amount from $from (can be label or key of a contract, account or identitiy) to $to (can be a label, or any valid key)
Note: $fee and $parameter aren't implemented yet

#### eztz typecheckCode $code
Typechecks code
Note: Code doesn't handle sugars yet (DIIP etc).

#### eztz typecheckData $data $type
Typechecks $data against the specified $type

#### eztz runCode $code $amount $input $storage
Simulates running $code with initial $storage, with a transaction of $amount and $input.
Note: $trace variable is ignored (alway true). Code doesn't handle sugars yet (DIIP etc).

#### eztz contract $contract
Returns the contract/account JSON object for $contract
Note: object data could do with some tidying up

#### eztz storage $contract
Returns the storage for $contract - data is returned as a formatted array (more details to come).
Note: Needs work on display format

#### eztz head
Returns the current head JSON object
Note: object data could do with some tidying up

#### eztz rpc $endPoint
Calls the RPC api at the $endPoint specified, using the $data (if any)
Note: $data hasn't been implemented yet

#### eztz provider $provider
Changes the node provider - by default we use https://tezrpc.me/api. You could set this to something like localhost:8732


## Future Development
Our current goals are:
* Implement optional arguments
* Work on documentation
* Change commands to match tezos client (i.e. get balance for X and transfer 50000 to A from V)
* Further debugging
* Optimize build and implement tests
* Improve CLI with something like commander
* Add better CLI GUI (colours, error messages, tables etc)
* Develop CLI help and man guides
* Expand functionality to fully match tezos-client (currently we got about 85% of functionality)

## Contribute
Please feel free to contribute - I will merge any pull requests as soon as I've gone through the changes.

## Author
By Stephen Andrews, and produly developed at Cryptonomic!

## Support Us
Please consider donating to help me develop this and other Tezos related tools, I currently rely on the kindness of others.

Bitcoin: 1KSiyfgs5XwTZjaLpmCTHxonsyXMx383P1

## Credits
https://github.com/stephenandrews/eztz (eztz.js)

## License
MIT
