***
**Functional Dependencies**: A statement about all allowable instances

###### Evils of Redundancy
**Update Anomaly**: Need to change more than 1 thing to stay consistent
**Insertion Anomaly**: Attributes cannot be inserted without the presence of other attributes
**Deletion Anomaly**: Attributes are lost because of deletion of other attributes


###### Deriving Additional FDs:
**Closure of F (F⁺):** all functional dependencies you can **derive or infer** from the given ones using the basic rules (reflexivity, augmentation, transitivity).
- **Reflexivity:**  
    If a set of attributes includes another set, it functionally determines it.  
    → If `Y ⊆ X`, then `X → Y`.  
    **Example:** `{A, B} → A` (because A is part of {A, B}).
- **Augmentation:**  
    You can add the same attributes to both sides of a dependency.  
    → If `X → Y`, then `XZ → YZ`.  
    **Example:** `A → B` ⇒ `AC → BC`.
- **Transitivity:**  
    You can link dependencies through a shared attribute.  
    → If `X → Y` and `Y → Z`, then `X → Z`.  
    **Example:** `A → B` and `B → C` ⇒ `A → C`.
**Union:**  
If two FDs have the same left side, you can combine their right sides.  
→ If `X → Y` and `X → Z`, then `X → YZ`.  
**Example:** `A → B` and `A → C` ⇒ `A → BC`.

**Decomposition:**  
If an FD has multiple attributes on the right, you can split it.  
→ If `X → YZ`, then `X → Y` and `X → Z`.  
**Example:** `A → BC` ⇒ `A → B` and `A → C`.