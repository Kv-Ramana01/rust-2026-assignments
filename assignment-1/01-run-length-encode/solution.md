# Solution notes: Run-length encode

## Approach

I iterated through the string one character at a time while keeping track of the current character and the number of times it appeared consecutively.

If the next character matched the current one, I incremented the count. Otherwise, I stored the current `(character, count)` pair in the result vector and started counting a new run. After the loop, I added the final run to the result.

## Edge cases handled

- Empty string returns an empty vector.
- Single-character strings return a single `(char, 1)` pair.
- Strings with all identical characters are compressed into one pair.
- Strings with no repeated characters produce a count of `1` for each character.

## Anything special

The algorithm runs in **O(n)** time, where `n` is the number of characters in the input string, and uses **O(k)** additional space, where `k` is the number of character runs. It works directly with `input.chars()`, so it correctly handles Unicode characters.