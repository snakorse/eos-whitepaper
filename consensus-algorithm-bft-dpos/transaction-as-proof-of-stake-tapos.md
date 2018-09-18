# 权益证明交易\(TaPos\)

> ## Transaction as Proof of Stake \(TaPoS\)

EOS.IO软件要求每一笔交易都要包含最近的一个区块投的的hash值。这个hash值有两个目的：

1. 避免在不包含这个区块的分叉上发生重放攻击；
2. 通知网络特定的用户和他的权益在特定的分叉上。

> The EOS.IO software requires every transaction to include part of the hash of a recent block header. This hash serves two purposes:
>
> 1. prevents a replay of a transaction on forks that do not include the referenced block; and
> 2. signals the network that a particular user and their stake are on a specific fork.

随着时间推移，所有用户最终都直接确认了区块链，这使得伪造假链变得困难，因为假链无法从合法的链上转移交易。

> Over time all users end up directly confirming the blockchain which makes it difficult to forge counterfeit chains as the counterfeit would not be able to migrate transactions from the legitimate chain.



