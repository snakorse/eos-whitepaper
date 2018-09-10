# 公式算法 \(BFT-DPOS\)

> #### Consensus Algorithm \(BFT-DPOS\)

---

EOS.IO软件利用了唯一已知的分散共识算法，该算法能够满足区块链上应用程序的性能要求，授权的证据（DPOS）。在这种算法下，那些在采用了EOS.IO软件的区块链上持有token的人可以通过一个连续的批准投票系统来选择块生产者。任何人都可以选择参与区块生产，并将有机会生产区块，只要他们能说服token持有者投票给他们。

> EOS.IO software utilizes the only known decentralized consensus algorithm proven capable of meeting the performance requirements of applications on the blockchain, [Delegated Proof of Stake \(DPOS\)](https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper). Under this algorithm, those who hold tokens on a blockchain adopting the EOS.IO software may select block producers through a continuous approval voting system. Anyone may choose to participate in block production and will be given an opportunity to produce blocks, provided they can persuade token holders to vote for them.

EOS.IO软件保证了每0.5秒产生一个区块，且在任何时间点只有一个生产者可以被授权生产区块。如果在预设的时间点没有区块产生，那么这个时间槽对应的区块将被跳过。每一个被跳过的区块，都会在区块链上行程一个时间空隙。

> The EOS.IO software enables blocks to be produced exactly every 0.5 second and exactly one producer is authorized to produce a block at any given point in time. If the block is not produced at the scheduled time, then the block for that time slot is skipped. When one or more blocks are skipped, there is a 0.5 or more second gap in the blockchain.

===

> Using the EOS.IO software, blocks are produced in rounds of 126 \(6 blocks each, times 21 producers\). At the start of each round 21 unique block producers are chosen by preference of votes cast by token holders. The selected producers are scheduled in an order agreed upon by 15 or more producers.

===

> If a producer misses a block and has not produced any block within the last 24 hours they are removed from consideration until they notify the blockchain of their intention to start producing blocks again. This ensures the network operates smoothly by minimizing the number of blocks missed by not scheduling producers who are proven to be unreliable.

===

> Under normal conditions a DPOS blockchain does not experience any forks because, rather than compete, the block producers cooperate to produce blocks. In the event there is a fork, consensus will automatically switch to the longest chain. This method works because the rate at which blocks are added to a blockchain fork is directly correlated to the percentage of block producers that share the same consensus. In other words, a blockchain fork with more producers on it will grow in length faster than one with fewer producers, because the fork with more producers will experience fewer missed blocks.

===

> Furthermore, no block producer should be producing blocks on two forks at the same time. A block producer caught doing this will likely be voted out. Cryptographic evidence of such double-production may also be used to automatically remove abusers.

===

> Byzantine Fault Tolerance is added to traditional DPOS by allowing all producers to sign all blocks so long as no producer signs two blocks with the same timestamp or the same block height. Once 15 producers have signed a block the block is deemed irreversible. Any byzantine producer would have to generate cryptographic evidence of their treason by signing two blocks with the same timestamp or blockheight. Under this model a irreversible consensus should be reachable within 1 second.



