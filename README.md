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
Check out the wiki: https://github.com/stephenandrews/eztz-cli/wiki

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
* Develop baker/endorser daemon services
* Build multi-platform GUI (light-client)

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
