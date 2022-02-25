# Unobtanium Address Indexer in Rust

An efficient addresses indexer based on [Electrs](https://github.com/romanz/electrs) by [Roman Zeyde](https://github.com/romanz).

The server indexes the entire Unobtanium blockchain, and the resulting index enables fast queries allowing to keep real-time track of the transaction history of Unobtanium addresses. Since it runs on the user's own machine, there is no need for the wallet to communicate with external servers, thus preserving the privacy of the user's addresses and balances.

## Features

 * Maintains an index over transaction inputs and outputs, allowing fast queries of the history of a Unobtanium address
 * Fast synchronization of the Unobtanium blockchain (~2 hours for ~187GB @ July 2018) on [modest hardware](https://gist.github.com/romanz/cd9324474de0c2f121198afe3d063548)
 * Low index storage overhead (~20%), relying on a local full node for transaction retrieval
 * Efficient mempool tracker
 * Low CPU & memory usage (after initial indexing)
 * Uses a single [RocksDB](https://github.com/spacejam/rust-rocksdb) database, for better consistency and crash recovery

## Usage

See [here](doc/usage.md) for installation, build and usage instructions.

## Index database

The database schema is described [here](doc/schema.md).
