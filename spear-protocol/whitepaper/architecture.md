# Architecture

The DCS Theorem states that decentralized consensus systems such as blockchains can have Decentralization, Consistency, or Scalability, but not all three properties simultaneously. To get around the DCS Triangle, Slepak et. al proposed two approaches:

1. Combining DC and DS systems – usually implemented by overlaying a fast DS system over a slower DC system such as the Lightning network and Bitcoin.
2. Combining multiple DC systems – also known as sharding, consensus participants form smaller groups to distribute the workload and enable parallelization.

<figure><img src="../../.gitbook/assets/DC + DS.PNG" alt=""><figcaption><p>Combination of a DC system and a DS system</p></figcaption></figure>

We propose a third approach which combines a DC system with multiple fast and generalized DS systems. Below we show a diagram of this proposed system, then we list and describe the actors participating in the system, the layers and chain structure of the network, and finally how sharding is implemented to boost scalability.\


<figure><img src="../../.gitbook/assets/SPEAR v2 Architecture-System.png" alt=""><figcaption><p>Combination of a DC system with multiple DS systems</p></figcaption></figure>

### Actors&#x20;

* Block Producers
  * Becomes eligible to produce blocks by staking their own Dory NFT and Aspi tokens on the Apella layer or receive staking delegation from other accounts.
  * Requires powerful machines with a high-bandwidth connection to run the block production node software module capable of validating thousands of transactions per second and sufficient disk space to store the blockchain state.&#x20;
  * A small number (between 7 to 23) of nodes is randomly selected per epoch to minimize latency and improve block propagation.
* Witnesses
  * A relatively small subset of validators (between 100 to 300) who are randomly chosen to form a committee that will oversee block production for a limited duration of time.
  * Witnesses are reshuffled in an overlapping fashion relative to the block production epoch to ensure smooth operation and handover when block producers are reassigned.
  * A _superblock_ is considered valid if it receives attestations (digital signatures) from 2/3 of the current witnesses set.&#x20;
* Validators
  * Eligible to participate in block production on the Apella layer by staking a fixed amount of Aspi or receiving delegated staking power. Dory NFT owners are exempted from the need for staking Aspi to become validators.
  * One validator is randomly derived when a miner creates an empty block header via the Khimaira algorithm which means that validators need to be constantly online to earn block rewards
  * Requires modestly powerful computers compared to block producers but still capable of validating transactions on the Apella layer or validating the state on the Stratos layer if selected to serve as a Witness in the next epoch.&#x20;
  * There is no limit to the number of validators on the Apella layer as anyone with enough stake and technical capacity can participate.
* Miners
  * Creates an empty block header by trying to solve the Proof of Work (PoW) puzzle to earn a block reward.
  * Can use computers with modest specs for mining as the PoW part under the Khimaira mechanism which utilizes RandomX, an ASIC-resistant PoW algorithm.
* Governors
  * Delegates that vote and decide on the parameters of all Execution Chains present on the network.
* DAO Members
  * Any user that has an account that holds either Dory NFTs or Aspi tokens.
  * By staking their tokens, can have other roles in the network such as a Validator, Witness, Governor, or Block Producer.
  * Can delegate their staking power to other accounts if the user doesn’t wish to act as a Consensus or Governance participant.
  * Receive voting power that is proportional their staked tokens which can be used to vote for community proposals or delegate to a Governance Delegate.

### Layers

We employ a novel sharded multi-layer architecture that enables both vertical and horizontal scaling while maintaining high decentralization and security. The figure below illustrates the actors responsible for consensus as well as the functionalities available to those actors in each layer.

![SPEAR Architecture Layers](<../../.gitbook/assets/SPEAR v2 Architecture-Layers.png>)

* Mora - a small group of high performance nodes randomly chosen in proportion to their staking power which are in charge of producing blocks with instant finality (non-reversible after a few seconds) and high throughput (capable of thousands of transactions per second).
* Stratos - forms a DS system in conjunction with the Mora layer, where a committee of witnesses is randomly selected from the the staked validators on the Apella layer tasked with creating checkpoints and provides shared security across all DS systems in the network.
* Apella - serves as the DC system designed for maximum security and decentralization via the Khimaira consensus mechanism which provides a strong foundation for DAO voting, staking, and delegation for Consensus and Governance participants.
* Ethereum - a set of smart contracts on the Ethereum mainnet for NFT staking, ERC-20 non-custodial bridging, and XUSD RToken collateral management.

### Structure

![SPEAR blockchain structure](<../../.gitbook/assets/SPEAR v2 Architecture-Chains Extended.png>)

#### Block Production Chain&#x20;

* Chain implementation of the Mora layer that uses Tendermint, a fast consensus mechanism with instant finality.
* EVM-compatible and can achieve around >1,000 TPS with \~7 second block time with instant finality (cannot be reverted).
* Valid blocks require 2/3+ of the voting power from the current set of Block Producers.

#### Checkpoint Chain

* Chain implementation of the Stratos layer that implements Spearmint, a consensus mechanism based on Tendermint, to create _superblocks_ from a set of blocks from the Block Production Chain.
* Witnesses review and collate a set number of blocks from Block Producers and submit these as _superblocks_ to the Chronicle Chain.
* _Superblocks_ are synonymous with checkpoints on the Polygon (formerly Matic) network, and requires valid attestations from 2/3+ of the Witnesses in a committee.
* A committee of 100 to 300 Witnesses are randomly chosen from the full set of Validators that have staked their tokens on the Chronicle Chain.

#### Chronicle Chain&#x20;

* Chain implementation of the Apella layer optimized for Decentralization and Security.
* Implements the Khimaira consensus mechanism that uses the RandomX algorithm for ASIC-resistance.
* Block time of 5 minutes and a block size limit of 300KB.
* Difficulty Adjustment (DA) period of 2 weeks similar to Bitcoin but with enhanced DA formula that includes the orphan rate.
* Employs NC-Max algorithm to improve block propagation latency.
* Block space is divided into governance (no fees) and non-governance (with fees) transactions.
* Only DAO members can submit transactions .
* Smart Contracts on the Chronicle Chain need a super majority vote from the SPEAR DAO to be added to the blockchain.
* Stores checkpoints for all shards, including relay shards.

#### Execution Chains

* Combination of the Checkpoint and Block Production Chains to simplify the notation and illustration of the DS part of the system.

<figure><img src="../../.gitbook/assets/SPEAR v2 Architecture-Chains.png" alt=""><figcaption><p>Execution Chain Structure</p></figcaption></figure>

### Scalability

An advantage of SPEAR Protocol’s multi-layered design is that it is compatible with sharding which allows horizontal scalability by simply adding more Execution Chains as shards. This sharded structure is demonstrated in the figure below:

<figure><img src="../../.gitbook/assets/SPEAR v2 Architecture-Sharding.png" alt=""><figcaption><p>Sharded view of the SPEAR network</p></figcaption></figure>

#### Shard Chains

* When there are multiple Execution Chains, a standard Execution Chain is called a Shard Chain.
* The SPEAR DAO Governors vote to initialize a new shard and determine the chain's parameters.
* Shard Chains can have different properties e.g. shards could either be  EVM-compatible or not.
* Shard Chain witnesses and block producers stake their tokens in a smart contract on the Chronicle Chain.

#### Relay Chains

* A special type of Shard Chain where block producers receive and transmit cross-shard transactions between multiple Shard Chains.
* Allow the throughput of the cross-shard transactions to match the Shard Chains instead of using the much slower Chronicle Chain for exchanging messages between Shard Chains.
* The SPEAR DAO can deploy multiple Relay Chains to improve the routing of cross-shard transactions once the number of Shard Chains increases significantly.
