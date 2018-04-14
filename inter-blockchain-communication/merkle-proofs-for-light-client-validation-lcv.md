## Merkle Proofs for Light Client Validation \(LCV\)

> #### Merkle Proofs for Light Client Validation \(LCV\)

---

===

> Integrating with other blockchains is much easier if clients do not need to process all transactions. After all, an exchange only cares about transfers in and out of the exchange and nothing more. It would also be ideal if the exchange chain could utilize lightweight merkle proofs of deposit rather than having to trust its own block producers entirely. At the very least a chain's block producers would like to maintain the smallest possible overhead when synchronizing with another blockchain.

===

> The goal of LCV is to enable the generation of relatively light-weight proof of existence that can be validated by anyone tracking a relatively light-weight data set. In this case the objective is to prove that a particular transaction was included in a particular block and that the block is included in the verified history of a particular blockchain.

===

> Bitcoin supports validation of transactions assuming all nodes have access to the full history of block headers which amounts to 4MB of block headers per year. At 10 transactions per second, a valid proof requires about 512 bytes. This works well for a blockchain with a 10 minute block interval, but is no longer "light" for blockchains with a 0.5 second block interval.

![](https://camo.githubusercontent.com/d1247e97697c62a84ed549bb9b00f601beb013a0/687474703a2f2f656f732e696f2f7770696d672f4469616772616d312e6a7067)

===

> The EOS.IO software enables lightweight proofs for anyone who has any irreversible block header after the point in which the transaction was included. Using the hash-linked structure shown it is possible to prove the existence of any transaction with a proof less than 1024 bytes in size.

===

> Given any block id for a block in the blockchain, and the headers a trusted irreversible block. It is possible to prove that the block is included in the blockchain. This proof takes ceil\(log2\(N\)\) digests for its path, where N is the number of blocks in the chain. Given a digest method of SHA256, you can prove the existence of any block in a chain which contains 100 million blocks in 864 bytes.

===

> There is little incremental overhead associated with producing blocks with the proper hash-linking to enable these proofs which means there is no reason not to generate blocks this way.

===

> When it comes time to validate proofs on other chains there are a wide variety of time/ space/ bandwidth optimizations that can be made. Tracking all block headers \(420 MB/year\) will keep proof sizes small. Tracking only recent headers can offer a trade off between minimal long-term storage and proof size. Alternatively, a blockchain can use a lazy evaluation approach where it remembers intermediate hashes of past proofs. New proofs only have to include links to the known sparse tree. The exact approach used will necessarily depend upon the percentage of foreign blocks that include transactions referenced by merkle proof.

===

> After a certain density of interconnectedness, it becomes more efficient to simply have one chain contain the entire block history of another chain and eliminate the need for proofs all together. For performance reasons, it is ideal to minimize the frequency of inter-chain proofs.



