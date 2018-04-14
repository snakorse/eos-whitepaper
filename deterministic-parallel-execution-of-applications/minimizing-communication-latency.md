## Minimizing Communication Latency

> #### Minimizing Communication Latency

---

===

> Latency is the time it takes for one account to send an Action to another account and then receive a response. The goal is to enable two accounts to exchange Actions back and forth within a single block without having to wait 0.5 seconds between each Action. To enable this, the EOS.IO software divides each block into cycles. Each cycle is divided into shards and each shard contains a list of transactions. Each transaction contains a set of Actions to be delivered. This structure can be visualized as a tree where alternating layers are processed sequentially and in parallel.

```
  Block

    Region

      Cycles (sequential)

        Shards (parallel)

          Transactions (sequential)

            Actions (sequential)

              Receiver and Notified Accounts (parallel)
```

===

> Transactions generated in one cycle can be delivered in any subsequent cycle or block. Block producers will keep adding cycles to a block until the maximum wall clock time has passed or there are no new generated transactions to deliver.

===

> It is possible to use static analysis of a block to verify that within a given cycle no two shards contain transactions that modify the same account. So long as that invariant is maintained a block can be processed by running all shards in parallel.



