# Introduction to Blockchain

### Decentralization

Distributes decision-making power across entities instead of a single authority.

> I like having a chain of bank without the central bank

### Consensus algorithms

Are the way those decisions are reached within the chain

## Consensus algorithms

The most critical element of a blockchain thecnology.
Comes from the study of distribuited systems in the computer science field

### The Byzantine General Problem

https://www.youtube.com/watch?v=A-mNgqJETQg

https://www.youtube.com/watch?v=dfsRQyYXOsQ

The generals need an algorithm they can follow to guarantee that all loyal generals decide
upon the same plan of action. The agreement the generals reach is called consensus, and
they reach it with a consensus algorithm.

However, some of the generals may be traitors working for the enemy. They may spread
false information to prevent agreement on a common plan. Therefore, the loyal generals
need an algorithm designed in such a way that consensus is achieved even if there are
unreliable or traitorous generals

**Transaction throughput**

> The rate decisions are made. Decisions are commited transactions. Example: If the network can make 1 decision per 10 minutes the rate is 0.0016 decisions per second.

**Latency**

> Taking the Byzantine generals. Latency refers to the time a general first announces a decision, a proposal, to the time the last general makes the final decision.
> Applying the blockchain concepts the latency would be when a transaction starts and when is commited to the network

#### Crash Fault-Tolerant and Byzantine Fault-Tolerant Consensus Algorithms

How to reach consensus even if some of the components fail? CFT is a subset of BFT

> BFT means the system must continue reaching consensus even when a component fails or crashs

## Bitcoin whitepaper (2008)

Bitcoin network launched in 2009
and using proof of X
