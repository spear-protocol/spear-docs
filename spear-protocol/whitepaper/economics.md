# Economics

### Triple Token Design&#x20;

* Dory (NFT) for bootstrapping the network
* Aspi (volatile token) for staking and root chain fees if not stablecoin is available&#x20;
* XUSD (stablecoin) for transaction fees on shards

### Issuance

* Bitcoin’s capped supply is an advantage based on game-theory but creates security issues once the block reward becomes zero&#x20;
* Inflation would encourage system actors to try to use their Aspi for staking to earn more rewards instead of just holding&#x20;
* 105,120 blocks expected per year (5 mins per block)
* In 20 years, the inflation rate will be less than 1% and continue to be decreasing per year moving forward

| Halving (every 5 years) | PoW | PoS  | Total Supply |
| ----------------------- | --- | ---- | ------------ |
| 0                       | 40  | 20   | 31,536,000   |
| 1                       | 20  | 10   | 47,304,000   |
| 2                       | 10  | 5    | 55,188,000   |
| 3                       | 5   | 2.5  | 59,130,000   |
| 4                       | 2.5 | 1.25 | 61,101,000   |

### Dual Difficulty Adjustment

* 4,032 blocks per 2 weeks
* If more than expected, increase difficulty
* If less than expected, lower difficulty
* If equal expected, keep difficulty
* Consider orphan rate sa DA equation
* Reward Difficulty Adjustment
  * Every 24 hours&#x20;
  * If more than expected, reduce issuance PoW reward
  * If less than expected, increase issuance PoW reward

### Staking

* Validators need to stake Aspi to become a validator on the Apella layer
* Required amount staking could be decreased only via DAO voting
* Set minimum stake for initiator of the validator (30% - 50%)

### Incentives

TODO:

* [ ] How to incentivize proper block creation on Apella layer
* [ ] How slashing works for byzantine nodes on the Stratos and Mora layers

### Transaction Fees

TODO:&#x20;

* [ ] Describe how transaction fees are implemented on each layer.

### Taxes

TODO:

* [ ] Explain how taxes are set and enforced by the Fiscal Governance voting

