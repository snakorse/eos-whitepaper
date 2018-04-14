### Evaluating Permissions

> #### Evaluating Permissions

---

===

> When delivering an Action of type "**Action**", from **@alice **to **@bob **the EOS.IO software will first check to see if **@alice **has defined a permission mapping for **@bob.groupa.subgroup.Action**. If nothing is found then a mapping for **@bob.groupa.subgroup **then **@bob.groupa**, and lastly **@bob **will be checked. If no further match is found, then the assumed mapping will be to the named permission group **@alice.active**.

===

> Once a mapping is identified then signing authority is validated using the threshold multi-signature process and the authority associated with the named permission. If that fails, then it traverses up to the parent permission and ultimately to the owner permission, **@alice.owner**.

![](https://camo.githubusercontent.com/8cd91b490fed0c94369251791eb25d74bcf54460/687474703a2f2f656f732e696f2f7770696d672f6469616772616d32677261797363616c65322e6a7067)

