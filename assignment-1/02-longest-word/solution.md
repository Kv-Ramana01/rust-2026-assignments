# Solution notes: Longest word slice

## Approach

I used `split_whitespace()` to iterate over each word in the input sentence. Since `split_whitespace()` returns `&str` slices that borrow from the original string, no new `String` is allocated.

I kept track of the longest word seen so far using an `Option<&str>`. For each word, I compared its length with the current longest word. If it was longer, I updated the stored reference. If two words had the same length, I kept the first one by only updating when the new word was **strictly longer**.

## Edge cases handled

* Empty string returns `None`.
* Whitespace-only input returns `None`.
* Single-word input returns that word.
* If multiple words have the same maximum length, the first one is returned.

## Anything special

The solution runs in **O(n)** time, where `n` is the length of the input string, and uses **O(1)** extra space. It satisfies the requirement of returning a borrowed `&str` without allocating a new `String`.
