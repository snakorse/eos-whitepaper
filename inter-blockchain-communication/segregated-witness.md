## Segregated Witness

> #### Segregated Witness

---

===

> The concept of Segregated Witness \(SegWit\) is that transaction signatures are not relevant after a transaction is immutably included in the blockchain. Once it is immutable the signature data can be pruned and everyone else can still derive the current state. Since signatures represent a large percentage of most transactions, SegWit represents a significant savings in disk usage and syncing time.

===

> This same concept can apply to merkle proofs used for inter-blockchain communication. Once a proof is accepted and irreversibly logged into the blockchain, the 2KB of sha256 hashes used by the proof are no longer necessary to derive the proper blockchain state. In the case of inter-blockchain communication, this savings is 32x greater than the savings on normal signatures.

===

> Another example of SegWit would be for Steem blog posts. Under this model a post would contain only the sha256\(blog content\) and the blog content would be in the segregated witness data. The block producer would verify that the content exists and has the given hash, but the blog content would not need to be stored in order to recover the current state from the blockchain log. This enables proof that the content was once known without having to store said content forever.



