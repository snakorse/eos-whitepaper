## Separating Authentication from Application

> #### Separating Authentication from Application

---

===

> To maximize parallelization opportunities and minimize the computational debt associated with regenerating application state from the transaction log, EOS.IO software separates validation logic into three sections:
>
> 1. Validating that an Action is internally consistent;
> 2. Validating that all preconditions are valid; and
> 3. Modifying the application state.

===

> Validating the internal consistency of a Action is read-only and requires no access to blockchain state. This means that it can be performed with maximum parallelism. Validating preconditions, such as required balance, is read-only and therefore can also benefit from parallelism. Only modification of application state requires write access and must be processed sequentially for each application.

===

> Authentication is the read-only process of verifying that an Action can be applied. Application is actually doing the work. In real time both calculations are required to be performed, however once a transaction is included in the blockchain it is no longer necessary to perform the authentication operations.



