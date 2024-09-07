# What is blockchain

Is the technology to create decentralized applications. Is more than just cryptocurrencies and finance.
Blockchain technology is also referred to as Distributed Ledger Technology or DLT

> DAO - Decentralized Autonomous Organization

## Use cases

- Empowering p2p transactions
- Improving supply chain management and logistics tracking
- Manegaing identity
- Facilitating e-voting

## The main components of a blockchain: Blocks

### Blocks:

- Contain verified transcations linked to each other in a chin in chorological order.
- Transactions cannot be altered;
- Has a Header and Body.

#### The block header

Contains hash of previous block, time stamp, proof of body

#### The block body

Contains transaction data. Like payment data.

#### What is the header hash?

Uses a hash function that takes an arbitraty length data and transforms into a fixed length output called hash digest. Is a way to compress data.

#### How blocks are chained together?

Using the hash of the previous block. The next block has the hash of the previous block making it the blocks to chain in chronological order.

If a block is altered the network will reject that block.
