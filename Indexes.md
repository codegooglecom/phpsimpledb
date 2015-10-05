Indexes are important to Filters & Orders, anything not specified in **`$__indexes`** cannot be searched or sorted.

Updating/Altering **`$__indexes`** is supported but all previous entries are not re-indexed when a new index is present. This may change when I have more time to code a fix for this.