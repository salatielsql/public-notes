# Other approaches to consensus

> Protocols can combine algorithms creating hybrid proof-based consensus

## Proof of Authority

Still relies on social capital so participants must invest heavily

**How it works:**

- Implements a reputation-based algorithm to validate transactions and generate new blocks
- Validators act as moderators within the blockchain system
- Validators a typically investors or partners selected by other network participants
- Validators identities as usually disclosed to ensure full accountability

**Drawbacks:**

- Can be considered centralized due the validators selection process

**Best fit for:**

- Private permissioned blockchains
- Consortiums that publicly disclose their primary stakeholders

- [] What is Consortiums?

**Example protocols:**

- VeChain
- Xodex
- TomoChain

## Proof of Activity

Proposed in 2014, proof of activity, combines PoW and PoS.

**How it works:**

- Has two types of nodes: Miners and Validators
- Miners try to produce a block finding the correct hash nonce
- Validators are selected based on their stake
- Transactions fees are Splitted between Miners and Validators

**Example protocols:**

- Decred
- Espers

## Proof of Importance (PoI)

PoI is a proof-of-stake-based protocol

**How it works:**

- It tries to evaluate nodes' contributions rather than focusing solely on nodes' stake for participation in consensus
- The "importance" parameters varies from protocol to protocol
- For some protocols the concept of importance can be, for example, level of connectivity with other nodes or how many block they produced recently

**Example protocols:**

- New Economy Movement (NEM project)

## Proof of Burn (PoB)

**How it works:**

- Block producers have to virtually destroy their coins to get the right to produce a block
- The chance to be selected as the next block producer is directly related to the quantity of burnt tokens
- Required far less energy than classic PoW
- Miners have to burn tokens regularly to keep their block producing rights

**Example protocols:**

- Counterparty
- Slimcoin
- Factom

## Proof of Capacity (PoC) / Proof of Space (PoSpace)

**How it works**

- Block producers must invest in hard disk storage
- Much cheaper than computer devices for PoW
- Generates large datasets called plots on the hard disks
- Block producers are selected based on quantity of plots stored on their hard disks
- Leader selection is directly related to the disk space the participant has

**Example protocols:**

- Signum
- SpaceMint
- Storj
- Permacoin
- Areweave
- Chia

## Proof of Elapsed Time (PoET)

Proposed by Intel

**How it works**

- Executed in a special environment: the Trusted Execution Environment (TEE)
- Uses Intel Software Gard Extensions (XGS)

**Example protocols:**

- Sawtooth Lake

## Proof of Contribution (PoCo)

**How it works**

- Monitor the contributions of active nodes in a network
- Block producers are selected based on the contribution value
- Must do a safe token deposit to participate in consensus
- Users validate the block produced results
- Transactions fees are splitted among users who could validate the block results and block producers

**Example protocols:**

- iExec
- ICON - Modifed version called Delegated Proof of Contribution (DPoCo)

## Proof of History (PoH)

**How it works**

- Has a built-in historical record that proves the specific moment in time every on-chain event occurred
- Each validator keep their own internal clock using a verifiable delay function (VDF) and sequential hashing
- Tries to reduce communication

**Example protocols**

- Solana

- [] Search more on PoH
