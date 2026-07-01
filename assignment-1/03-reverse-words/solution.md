# Solution notes: Reverse the word order

## Approach

I used `split_whitespace()` to split the input sentence into individual words while automatically ignoring extra whitespace. Then I reversed the order of the words using `rev()`, collected them into a vector, and joined them back together with a single space using `join(" ")`.

## Edge cases handled

* Empty string returns an empty string.
* Whitespace-only input returns an empty string.
* Leading and trailing whitespace is removed.
* Multiple consecutive spaces are collapsed into a single space in the output.
* Single-word input is returned unchanged.

## Anything special

The solution is concise and uses Rust's iterator methods to process the string efficiently. It runs in **O(n)** time, where `n` is the length of the input, and returns a new `String` as required.
