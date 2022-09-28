# Related Work

### DCS Theorem

Paper: [https://arxiv.org/ftp/arxiv/papers/1801/1801.04335.pdf](https://arxiv.org/ftp/arxiv/papers/1801/1801.04335.pdf)

Trent McConaghy [\[1\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn1) from BigchainDB published an excellent article called “The DCS Triangle — Decentralized, Consistent, Scalable. Pick any two! [\[2\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn2)” in Jun 2016. Shortly thereafter, Vitalik Buterin from Ethereum and Greg Slepak also made similar statements. Vitalik calls it “scalability trilemma” [\[3\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn3) or “blockchain trilemma”. By October 1977, Greg Slepak published the article the “DCS Theorem”, used the math language, proved this theorem, and later posted it at Cornell University in January 2018 [\[4\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn4).

In summary, the DCS triangle states that we can have any two of the three key attributes of blockchain: Decentralization; Consensus; Scalability, but not all three at the same time. Or, in other words, if we fixed an attribute, the other two attributes would compensate each other. For example, if we fixed the Decentralization attribute, and increase the Consensus, we would certainly have sacrificed the speed and scalability of the system. And vice versa.

February 2018, Trent McConaghy updated his article and listed some approach to get around the limitation of the DCS triangle including:

\- Improving the consensus protocol. Examples: Ouroboros \[Kiayias2017][\[5\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn5), Dfinity \[Hanke2018][\[6\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn6), Red Belly \[Crain2017], OmniLedger \[Kokoris2018][\[7\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn7)

\- Sharding so that each node only has a fraction of the compute or data workload. Example: \[EthSharding2018][\[8\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn8)

\- Independent networks/chains with “glue” connectors. Examples: Interledger \[Thomas2015][\[9\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn9), Cosmos \[Kwon2017][\[10\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn10), PolkaDot \[Wood2016][\[11\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn11), Plasma \[Poon2017][\[12\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn12), TrueBit \[Teusch2017][\[13\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn13)

\- “Layer 2” payment channels. Examples: Lightning \[Poon2016][\[14\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn14), Raiden \[Raiden2018][\[15\]](https://medium.com/amate/solving-the-blockchain-trilemma-91fa9ca4e007#\_ftn15)

In his article “DCS Theorem”, Greg Slepak also proposed two approaches to solve the problem:

\- Combining DC and DS systems: This is actually the state channels solution used in the Lightning Network and the Raiden Network as described above

\- Combining multiple DC systems: Also known as sharding, this approach is mentioned above in Ethereum Sharding and OmniLedger too.

### NC-Max

### Tendermint

Whitepaper: [https://github.com/cosmos/cosmos/blob/master/WHITEPAPER.md#introduction](https://github.com/cosmos/cosmos/blob/master/WHITEPAPER.md#introduction)

### Gasper

### Reserve RToken
