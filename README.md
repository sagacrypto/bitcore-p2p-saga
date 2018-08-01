Bitcore P2P-Saga
=======

[![NPM Package](https://img.shields.io/npm/v/@sagacrypto/bitcore-p2p-saga.svg?style=flat-square)](https://www.npmjs.org/package/@sagacrypto/bitcore-p2p-saga)
[![Build Status](https://img.shields.io/travis/sagacrypto/bitcore-p2p-saga.svg?branch=master&style=flat-square)](https://travis-ci.org/sagacrypto/bitcore-p2p-saga)
[![Coverage Status](https://img.shields.io/coveralls/sagacrypto/bitcore-p2p-saga.svg?style=flat-square)](https://coveralls.io/r/sagacrypto/bitcore-p2p-saga?branch=master)

`bitcore-p2p-saga` adds SagaCoin protocol support for Bitcore-Saga.

See [the main bitcore-saga repo](https://github.com/sagacrypto/bitcore-saga) for more information.

## Getting Started

```sh
npm install @sagacrypto/bitcore-p2p-saga
```
In order to connect to the SagaCoin network, you'll need to know the IP address of at least one node of the network, or use [Pool](/docs/pool.md) to discover peers using a DNS seed.

```javascript
var Peer = require('@sagacrypto/bitcore-p2p-saga').Peer;

var peer = new Peer({host: '127.0.0.1'});

peer.on('ready', function() {
  // peer info
  console.log(peer.version, peer.subversion, peer.bestHeight);
});
peer.on('disconnect', function() {
  console.log('connection closed');
});
peer.connect();
```

Then, you can get information from other peers by using:

```javascript
// handle events
peer.on('inv', function(message) {
  // message.inventory[]
});
peer.on('tx', function(message) {
  // message.transaction
});
```

Take a look at the [bitcore guide](http://bitcore.io/guide/peer.html) on the usage of the `Peer` class.

## Contributing

See [CONTRIBUTING.md](https://github.com/sagacrypto/bitcore-saga/blob/master/CONTRIBUTING.md) on the main bitcore-saga repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/sagacrypto/bitcore-p2p-saga/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
Copyright 2018 SagaCoin Development Team.
