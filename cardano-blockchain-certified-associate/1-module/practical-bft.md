# Practical Byzantine Fault Tolerance

## Fault Tolerace

Is a system's ability to keep working even when arbitrary faults or attack occurs

System that is resilient to failed can be considered BFT

Most blockchain systems is BFT or tends towards it

**Properties of a BFT Consensus Algorithm**

- Safety: ability of a distributed system to commit to the same value
- Liveness: ability of continuously commit to new values and make progress

## Synchrony vs Asynchronous systems

> Since the world is not binary there a wide hybrid situations in between

The internet is a example of asynchronous system where browers don't have a way to infer how much the server will take to respond therefore browsers most of them implement timeouts. Browesers also don't know how to differentiate a server not responding to a server taking to long to respond.

**Many Blockchain consensus protocols are synchronous**

> Bitcoin and Ouroboros consensus protocol are synchronous

- Bitcoin: mining block w/ a time frame
- Ouroboros: each node share a globally synchronized clock

## Sychronized Clock

Network Time Protocol (NTP) is a well-known internet protocal used to syncrhonize clocks of various machines

- [▶️ How quartz clocks works](https://www.youtube.com/watch?v=3jfgQF3jX7A)
- [▶️ How atomic clock works](https://www.youtube.com/watch?v=l8CI3bs9rvY)

> Impossible to find consensus in a **fully** asynchronous distributed system

**Example of asynchronous systems:**

- Paxos (Lamport and Al)
- PBFT (Castro and Liskov) - Cosmos, Binance Smart Chain and Hyperledger Fabric uses PBFT or some variant of it

## PBFT Overview

- Works in an almost asynchronous setting
- Is a state-machine replica

### Assumptions

**One third of the nodes can be faulty**

**Fully Byzantine situations**

Malicious actors of the system can delay messages and even coordinate communications between malicious nodes but it excludes adversaries from being able to delay communications indefinitely

> Userful to justify the protocal ensures liveness

**Non-collision and preimage resistance properties**

### Transaction commit (PBFT Algorithms)

To a transaction to be commited to the ledger these 3 steps must happen:

1. A client makes a request to a node of the system
2. The node must then foward the request to all other nodes
3. Each node then replies to the original client with the outcome of the executing the request

![Simplified PBFT Under Normal Operation Mode](../images/Simplified%20PBFT%20Under%20Normal%20Operation%20Mode.png)

[▶️ Video explaining PBFT](https://youtu.be/IafgKJN3nwU)

> This type of consensus is sometimes called **Vote-based Consensus**

**Vote-based Consensus**

- Making replicas actively confirming an outcome proposed buy a primary node
- Communication heavy
  Tendermint is a module PBFT consensus framework. Used by Cosmos.

> Primary nodes = _Block producers_

> Replica nodes = _Block validators_

### Vote-based Consensus limitations

- Challenges in term of network communication
- Each block production is by a much larger amount of votes to establish consensus
- The network used for consensus, it isn't used to transfer useful user data
- Does not scale well to even a 100 nodes
- Nodes have to be aware of each other ahead of time
- In practice adding a new node requires each existing node to ackownledge the change
- Inheritly federated
- Prone to Sybil Attacks _meaning is possible to a single actor to control more than one node_

![messaging overhead](../images/messaging%20overhead.png)

> A single request in a cluster of 4 nodes would require 24 messages, 8 nodes 71 messages and 13 nodes 237 messages
