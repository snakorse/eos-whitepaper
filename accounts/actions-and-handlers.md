## Actions & Handlers

> #### Actions & Handlers

---

===

> Each account can send structured Actions to other accounts and may define scripts to handle Actions when they are received. The EOS.IO software gives each account its own private database which can only be accessed by its own action handlers. Action handling scripts can also send Actions to other accounts. The combination of Actions and automated action handlers is how EOS.IO defines smart contracts.

===

> To support parallel execution, each account can also define any number of scopes within their database. The block producers will schedule transaction in such a way that there is no conflict over memory access to scopes and therefore they can be executed in parallel.



