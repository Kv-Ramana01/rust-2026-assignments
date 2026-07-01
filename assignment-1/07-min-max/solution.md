# Solution notes: `min_max`

## Approach

I first checked whether the input slice was empty. If it was, I returned `None`.

Otherwise, I initialized both the minimum and maximum values with the first element of the slice. Then I traversed the remaining elements using a single `for` loop. For each value, I compared it with the current minimum and maximum and updated them when necessary.

After processing all elements, I returned the pair `(min, max)` wrapped in `Some`.

## Edge cases handled

* Empty slice returns `None`.
* Single-element slice returns that value as both the minimum and maximum.
* Handles positive, negative, and duplicate values correctly.

## Anything special

The solution uses exactly one manual loop and does not rely on iterator helpers such as `.min()` or `.max()`, satisfying the assignment constraint. It runs in **O(n)** time and uses **O(1)** extra space.
