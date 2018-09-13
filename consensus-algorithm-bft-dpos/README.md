# 共识算法\(DPOS\)

> ## Consensus Algorithm \(BFT-DPOS\)

EOS.IO软件利用了唯一已知的分散共识算法，该算法能够满足区块链上应用程序的性能要求，授权的证据（DPOS）。在这种算法下，那些在采用了EOS.IO软件的区块链上持有token的人可以通过一个连续的批准投票系统来选择块生产者。任何人都可以选择参与区块生产，并将有机会生产区块，只要他们能说服token持有者投票给他们。

> EOS.IO software utilizes the only known decentralized consensus algorithm proven capable of meeting the performance requirements of applications on the blockchain, [Delegated Proof of Stake \(DPOS\)](https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper). Under this algorithm, those who hold tokens on a blockchain adopting the EOS.IO software may select block producers through a continuous approval voting system. Anyone may choose to participate in block production and will be given an opportunity to produce blocks, provided they can persuade token holders to vote for them.

EOS.IO软件保证了每0.5秒精确的产生一个区块，且在任何时间点只有一个生产者可以被授权生产区块。如果在预设的时间点没有区块产生，那么这个时间槽对应的区块将被跳过。每一个被跳过的区块，都会在区块链上行程一个时间空隙。

> The EOS.IO software enables blocks to be produced exactly every 0.5 second and exactly one producer is authorized to produce a block at any given point in time. If the block is not produced at the scheduled time, then the block for that time slot is skipped. When one or more blocks are skipped, there is a 0.5 or more second gap in the blockchain.

在EOS.IO中，一轮产生126个区块（21个生产者，每个产生6个区块）。在每轮的一开始，令牌拥有者选出21为不同的区块生产者。这21位生产者协商出一个大多数（15位或更多）都同意的顺序，并按照这个顺序来排队生成区块。

> Using the EOS.IO software, blocks are produced in rounds of 126 \(6 blocks each, times 21 producers\). At the start of each round 21 unique block producers are chosen by preference of votes cast by token holders. The selected producers are scheduled in an order agreed upon by 15 or more producers.

当某个生产者没有按约定执行时间产生区块，并且近24小时内也没有产生过任何区块，则会被从候选名单移除，直到它主动告知区块链其已经准备好重新生产区块。这种机制可以保证整个网络更平滑，尽量减少由于不可靠的生产者持续异常而导致错过的区块的数量。

> If a producer misses a block and has not produced any block within the last 24 hours they are removed from consideration until they notify the blockchain of their intention to start producing blocks again. This ensures the network operates smoothly by minimizing the number of blocks missed by not scheduling producers who are proven to be unreliable.

通常情况下，DPOS区块链不会出现分叉，因为区块生产者之间并不是竞争的关系，他们通过相互协作来生产区块。当出现分叉时，基于共识机制，生产者会自动切换到最长的链上。这种方式是有效的，因为区块链上新增区块的速度与采用同一共识的的区块生产者的占比直接相关。换句话说，被多数生产者采用的区块分叉链将会比只有少数生产者采用的分叉链长度增长的更快，因为拥有多数生产者的分叉链上会更少错过区块生产。

> Under normal conditions a DPOS blockchain does not experience any forks because, rather than compete, the block producers cooperate to produce blocks. In the event there is a fork, consensus will automatically switch to the longest chain. This method works because the rate at which blocks are added to a blockchain fork is directly correlated to the percentage of block producers that share the same consensus. In other words, a blockchain fork with more producers on it will grow in length faster than one with fewer producers, because the fork with more producers will experience fewer missed blocks.

而且，一个区块生产者同一时间只能在一个分叉上生产区块。如果某个生产者被发现这样做了，将很可能会被投票出局。这种双重生产行为对应的密码学凭证可以用来自动的删除这些捣乱者。

> Furthermore, no block producer should be producing blocks on two forks at the same time. A block producer caught doing this will likely be voted out. Cryptographic evidence of such double-production may also be used to automatically remove abusers.

通过允许所有的生产者对所有区块签名并保证只要没有生产者对两个区块签署相同的时间戳或同样的区块高度，传统的DPOS实现了 拜占庭容错。一单15个生产者对一个区块做了签名，这个区块将被认为是不可逆的。任何拜占庭生产者将必须必须为两个区块签署同样的时间戳或高度才能实现加密凭证的欺骗。在这种模型下，不可逆的共识将在1秒内完成。

> Byzantine Fault Tolerance is added to traditional DPOS by allowing all producers to sign all blocks so long as no producer signs two blocks with the same timestamp or the same block height. Once 15 producers have signed a block the block is deemed irreversible. Any byzantine producer would have to generate cryptographic evidence of their treason by signing two blocks with the same timestamp or blockheight. Under this model a irreversible consensus should be reachable within 1 second.



