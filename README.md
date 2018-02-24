# BitcoinJS (bitcoinjs-lib)
[![Build Status](https://travis-ci.org/bitcoinjs/bitcoinjs-lib.png?branch=master)](https://travis-ci.org/bitcoinjs/bitcoinjs-lib)
[![NPM](https://img.shields.io/npm/v/bitcoinjs-lib.svg)](https://www.npmjs.org/package/bitcoinjs-lib)
[![tip for next commit](https://tip4commit.com/projects/735.svg)](http://tip4commit.com/projects/735)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

This is a React Native compatible version of [bitcoinjs-lib,](https://github.com/bitcoinjs/bitcoinjs-lib)a pure JavaScript Bitcoin library for node.js and browsers.
Estimated to be in use by over 15 million wallet users and is the backbone for almost all Bitcoin web wallets in production today.


## Features
- Clean: Pure JavaScript, concise code, easy to read.
- Tested: Coverage > 90%, third-party integration tests.
- Careful: Two person approval process for small, focused pull requests.
- Compatible: Works on Node.js and all modern browsers.
- Powerful: Support for advanced features, such as multi-sig, HD Wallets.
- Secure: Strong random number generation, PGP signed releases, trusted developers.
- Principled: No support for browsers with crap RNG (IE < 11)
- Standardized: Node community coding style, Browserify, Node's stdlib and Buffers.
- Fast: Optimized code, uses typed arrays instead of byte arrays for performance.
- Experiment-friendly: Bitcoin Mainnet and Testnet support.
- Altcoin-ready: Capable of working with bitcoin-derived cryptocurrencies (such as Dogecoin).

## Installation
``` bash
npm i -S https://github.com/coreyphillips/react-native-bitcoinjs-lib
```

## Setup

### React Native
Install the following dependencies:
``` bash
npm i -S bitcoinjs-lib random-js buffer@5
npm i -D rn-nodeify
```
Add the following to your script in package.json: 

``` javascript
"postinstall": "./node_modules/.bin/rn-nodeify --install buffer,stream,assert,events --hack"
```

**Usage**
``` javascript
import "./shim";
const bitcoin = require("bitcoinjs-lib");
const keyPair = bitcoin.ECPair.makeRandom();
const address = keyPair.getAddress();
```

### Node.js
Use [bitcoinjs-lib](https://github.com/bitcoinjs/bitcoinjs-lib)

### Browser
Use [bitcoinjs-lib](https://github.com/bitcoinjs/bitcoinjs-lib)

## Examples
The below examples are implemented as integration tests, they should be very easy to understand.
Otherwise, pull requests are appreciated.
Some examples interact (via HTTPS) with a 3rd Party Blockchain Provider (3PBP).

- [Generate a random address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L12)
- [Generate an address from a SHA256 hash](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L19)
- [Import an address via WIF](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L29)
- [Generate a 2-of-3 P2SH multisig address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L36)
- [Generate a SegWit address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L50)
- [Generate a SegWit P2SH address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L60)
- [Generate a SegWit 3-of-4 multisig address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L71)
- [Generate a SegWit 2-of-2 P2SH multisig address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L86)
- [Support the retrieval of transactions for an address (3rd party blockchain)](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L100)
- [Generate a Testnet address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L121)
- [Generate a Litecoin address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/addresses.js#L131)
- [Create a 1-to-1 Transaction](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L14)
- [Create a 2-to-2 Transaction](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L28)
- [Create (and broadcast via 3PBP) a typical Transaction](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L46)
- [Create (and broadcast via 3PBP) a Transaction with an OP\_RETURN output](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L88)
- [Create (and broadcast via 3PBP) a Transaction with a 2-of-4 P2SH(multisig) input](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L115)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit P2SH(P2WPKH) input](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L151)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit 3-of-4 P2SH(P2WSH(multisig)) input](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/transactions.js#L183)
- [Import a BIP32 testnet xpriv and export to WIF](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L8)
- [Export a BIP32 xpriv, then import it](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L15)
- [Export a BIP32 xpub](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L26)
- [Create a BIP32, bitcoin, account 0, external address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L35)
- [Create a BIP44, bitcoin, account 0, external address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L50)
- [Create a BIP49, bitcoin testnet, account 0, external address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L66)
- [Use BIP39 to generate BIP32 addresses](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/bip32.js#L83)
- [Create (and broadcast via 3PBP) a Transaction where Alice can redeem the output after the expiry](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/cltv.js#L37)
- [Create (and broadcast via 3PBP) a Transaction where Alice and Bob can redeem the output at any time](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/cltv.js#L71)
- [Create (but fail to broadcast via 3PBP) a Transaction where Alice attempts to redeem before the expiry](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/cltv.js#L104)
- [Recover a private key from duplicate R values](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/crypto.js#L14)
- [Recover a BIP32 parent private key from the parent public key, and a derived, non-hardened child private key](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/crypto.js#L115)
- [Generate a single-key stealth address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/stealth.js#L70:)
- [Generate a single-key stealth address (randomly)](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/stealth.js#L89:)
- [Recover parent recipient.d, if a derived private key is leaked (and nonce was revealed)](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/stealth.js#L105)
- [Generate a dual-key stealth address](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/stealth.js#L122)
- [Generate a dual-key stealth address (randomly)](https://github.com/bitcoinjs/bitcoinjs-lib/blob/master/test/integration/stealth.js#L145)

If you have a use case that you feel could be listed here, please [ask for it](https://github.com/bitcoinjs/bitcoinjs-lib/issues/new)!


## Projects utilizing BitcoinJS
- [BitAddress](https://www.bitaddress.org)
- [Blockchain.info](https://blockchain.info/wallet)
- [Blocktrail](https://www.blocktrail.com/)
- [Dark Wallet](https://www.darkwallet.is/)
- [DecentralBank](http://decentralbank.com/)
- [Dogechain Wallet](https://dogechain.info)
- [EI8HT Wallet](http://ei8.ht/)
- [GreenAddress](https://greenaddress.it)
- [Helperbit](https://helperbit.com)
- [Melis Wallet](https://melis.io)
- [Robocoin](https://wallet.robocoin.com)
- [Skyhook ATM](http://projectskyhook.com)


## Contributing
We are always accepting of pull requests, but we do adhere to specific standards in regards to coding style, test driven development and commit messages.

Please make your best effort to adhere to these when contributing to save on trivial corrections.


### Running the test suite

``` bash
npm test
npm run-script coverage
```

## Complementing Libraries
- [BIP21](https://github.com/bitcoinjs/bip21) - A BIP21 compatible URL encoding library
- [BIP38](https://github.com/bitcoinjs/bip38) - Passphrase-protected private keys
- [BIP39](https://github.com/bitcoinjs/bip39) - Mnemonic generation for deterministic keys
- [BIP32-Utils](https://github.com/bitcoinjs/bip32-utils) - A set of utilities for working with BIP32
- [BIP66](https://github.com/bitcoinjs/bip66) - Strict DER signature decoding
- [BIP68](https://github.com/bitcoinjs/bip68) - Relative lock-time encoding library
- [BIP69](https://github.com/bitcoinjs/bip69) - Lexicographical Indexing of Transaction Inputs and Outputs
- [Base58](https://github.com/cryptocoinjs/bs58) - Base58 encoding/decoding
- [Base58 Check](https://github.com/bitcoinjs/bs58check) - Base58 check encoding/decoding
- [Bech32](https://github.com/bitcoinjs/bech32) - A BIP173 compliant Bech32 encoding library
- [coinselect](https://github.com/bitcoinjs/coinselect) - A fee-optimizing, transaction input selection module for bitcoinjs-lib.
- [merkle-lib](https://github.com/bitcoinjs/merkle-lib) - A performance conscious library for merkle root and tree calculations.
- [minimaldata](https://github.com/bitcoinjs/minimaldata) - A module to check bitcoin policy: SCRIPT_VERIFY_MINIMALDATA


## Alternatives
- [BCoin](https://github.com/indutny/bcoin)
- [Bitcore](https://github.com/bitpay/bitcore)
- [Cryptocoin](https://github.com/cryptocoinjs/cryptocoin)


## LICENSE [MIT](LICENSE)
