## Context Free Actions

> #### Context Free Actions

---

===

> A Context Free Action involves computations that depend only on transaction data, but not upon the blockchain state. Signature verification, for example, is a computation that requires only the transaction data and a signature to determine the public key that signed the transaction. This is one of the most expensive individual computations a blockchain must perform, but because this computation is context free it can be performed in parallel.

===

> Context Free Actions are like other user Actions, except they lack access to the blockchain state to perform validation. Not only does this enable EOS.IO to process all Context Free Actions such as signature verification in parallel, but more importantly, this enables generalized signature verification.

===

> With support for Context Free Actions, scalability techniques such as Sharding, Raiden, Plasma, State Channels, and others become much more parallelizable and practical. This development enables efficient inter-blockchain communication and potentially unlimited scalability.



