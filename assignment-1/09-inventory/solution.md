# Solution notes: Inventory

## Approach

For `restock`, I consumed both inventory vectors and merged their contents using a `HashMap<String, u32>`. Each item's quantity was added to the existing value if the item name was already present. Finally, I converted the `HashMap` back into a `Vec<(String, u32)>`.

For `summary`, I borrowed the inventory slice instead of taking ownership. I counted the number of inventory entries using `len()` and calculated the total quantity by summing the quantities. The function then returned a formatted string containing both values.

## Edge cases handled

* Empty inventories produce an empty merged inventory.
* Duplicate item names are combined by adding their quantities.
* `summary` correctly reports zero items and zero units for an empty inventory.
* The order of items in the merged inventory is unspecified, as allowed by the assignment.

## Anything special

The implementation demonstrates Rust's ownership model. `summary` only borrows the inventory, allowing it to be used afterward, while `restock` consumes its inputs so that `String` values can be moved into the `HashMap` without cloning. The merge operation runs in **O(n + m)** time, where `n` and `m` are the sizes of the two input inventories.
