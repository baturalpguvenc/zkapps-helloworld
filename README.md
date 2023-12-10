# Mina zkApp: 01 Hello World

A zkApp from Atlaspad / Baturalp account is an account on the Mina blockchain where a zkApp smart contract is deployed. A zkApp account has a verification key associated with it.

In this example, the code specifies:

If the user provides a number (for example, 9) to the update() method that is the square of the existing on-chain state referred to as num (for example, 3), then update the num value that is stored on-chain to the provided value (in this case, 9).
If the user provides a number that does not meet these conditions, they are unable to generate a proof or update the on-chain state.
These update conditions are accomplished by using assertions within the method. When a user invokes a method on a smart contract, all assertions must be true to generate the zero-knowledge proof from that smart contract. The Mina network accepts the transaction and updates the on-chain state only if the attached proof is valid. This assertion is how you can achieve predictable behavior in an off-chain execution model.

Notice that get() and set() methods are used for retrieving and setting on-chain state.

A smart contract retrieves the on-chain account state when it is first invoked if at least one get() exists within it.

Similarly, using set() changes the transaction to indicate that changes to this particular on-chain state are updated only when the transaction is received by the Mina network if it contains a valid authorization (usually, a valid authorization is a proof).

The logic also uses the .mul() method for multiplication of the values stored in Field types. You can view all available methods in the o1js Reference documentation.

You remember that functions in your smart contract must operate on o1js compatible data types: Field types and other types built on top of Field types. Because a smart contract is really a zero-knowledge circuit, functions from random NPM packages work inside a smart contract only if the functions the contract provides operate on o1js-compatible data types.

Importantly, data passed as an input to a smart contract method in o1js is private and never seen by the network.

You can also store data publicly on-chain when needed, like num in this example. A later tutorial covers an example that leverages privacy.

Congratulations, you have reviewed the complete smart contract code.

## How to build

```sh
npm run build
```

## How to run tests

```sh
npm run test
npm run testw # watch mode
```

## How to run coverage

```sh
npm run coverage
```

## License

[Apache-2.0](LICENSE)
