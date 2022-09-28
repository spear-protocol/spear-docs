# NFT Utility

### SPEAR DAO Membership

The SPEAR DAO will be the custodian of the SPEAR network and shall ensure its security against malicious actors and maintain its operational stability for the benefit of all users. Members of the SPEAR DAO shall be known as _Spartans_. To become a DAO member, an account must hold either:

* Dory, an NFT from the SPEAR Dory Collection
* Aspi, the native token of the Chronicle Chain

\
DAO membership will have the following benefits:

* Submit and vote on community proposals
* Assign voting power to a Governance Delegate$$^1$$
* Become a Governance Delegate$$^2$$ to vote for others
* Delegate staked token to a Consensus Delegate$$^3$$
* Become a Validator or a Block Producer via staking
* Receive a share of the DAO Treasury via a community proposal

\
Notes:&#x20;

1. _Governance Delegates are simply DAO members that receive voting power delegation from other DAO members._
2. _The SPEAR DAO will use a Liquid Democracy voting system where anyone can delegate and undelegate their voting power at any time. See the_ [_Governance_](https://docs.spear.technology/spear-protocol/whitepaper/governance) _section of the SPEAR Protocol whitepaper._
3. _Consensus Delegates are consensus participants such as Validators and Block Producers that receive staking power delegation from other DAO members._

### Pioneer DAO Delegates

To maximize decentralization and equitability, there will be no premine meaning Aspi tokens will not exist at genesis. Aspi will only originate from block rewards. Since all consensus mechanisms under the [Kerberos Protocol](https://docs.spear.technology/spear-protocol/whitepaper/consensus#kerberos) involves an element of Proof-of-Stake (PoS), there is a risk that an attacker can accumulate enough stake while the network is still young and the tokens are relatively cheap. This would give the malicious actor the ability to carry out a 51% attack on the network early on. \
\
There are two mechanisms that we will deploy to combat the scenario above:

* First, only accounts that hold a Dory NFT can become pioneer delegates for the duration between genesis and the first halving. They could either be a  Governance Delegate via voting power delegation, or a Consensus Delegate (Validator or Block Producer) via staking delegation.
* Second, an account that has just received a Dory NFT won't be eligible to become a delegate for a certain amount of time e.g. 12 months. This is so that an attacker cannot buy a majority of the NFTs and have controlling stake in the network while Aspi tokens are being fairly distributed to consensus participants.

### Persistent Account Pass

The SPEAR Protocol shall uphold decentralization at all costs. It is designed to enable anyone to run the node software for the Chronicle Chain ensuring all nodes in the network have a shared view of history. To this end, the growth of the required disk space to run a node would be throttled. One of the ways the protocol will achieve this is by using Dory NFTs as Persistent Account Passes (PAP) to slow down the increase of required storage for externally owned accounts on the Chronicle Chain. This would work as follows:

* Anyone can create an account on the Chronicle Chain similar to how an account is created on Ethereum.
* This new account can receive Aspi anytime from another externally owned account, smart contract, or from winning a block reward.
* If an account doesn't have a Dory NFT, it will be destroyed when it initiates a transfer transaction meaning the account owner would need to zero out its balance.
* Else if an account holds a Dory NFT, it is considered a persistent account and can receive and transfer normally as any Ethereum account.

The protocol above is meant to slow down the growth of accounts on the Chronicle Chain, not completely hinder it. So as part of the block reward for mining, each miner will receive a fungible PAP token called Kopis, allowing the number of accounts to grow by around 105,120 each year.  See the [Economics](https://docs.spear.technology/spear-protocol/whitepaper/economics) section of the SPEAR Protocol whitepaper.

### Profile Picture (PFP)

Last but not the least, each SPEAR Dory NFT is a limited-edition PFP for socially identifying with the SPEAR DAO. The holder of the NFT will have full copyright co-ownership (including commercial rights) to the artwork which is reassigned when a Dory NFT is transferred or traded.&#x20;

<figure><img src="../../.gitbook/assets/Sample Dory.jpg" alt=""><figcaption><p>SPEAR Dory NFT PFP</p></figcaption></figure>

Since the success or failure of the SPEAR project is not dependent on the value of the SPEAR brand, we are not considering to use the CC0 (Creative Commons Zero) for any of our NFT artworks now or in the future. Dory NFT holders will secure the SPEAR network at genesis serving as its caretakers so we want our initial supports to have true ownership of a piece of the network as members of the SPEAR DAO.&#x20;
