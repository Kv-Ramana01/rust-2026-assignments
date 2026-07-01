# Solution notes: Caesar cipher

## Approach

I declared the alphabet as a module-level constant and used `ALPHABET.len()` to determine the alphabet size instead of hard-coding `26`.

First, I normalized the shift using `rem_euclid()` so that both negative and large shift values wrap correctly within the alphabet. Then I iterated through each character in the input string.

For lowercase and uppercase ASCII letters, I calculated the character's position in the alphabet, applied the shift with wrapping, and converted it back to the corresponding character while preserving its case. Characters that are not ASCII letters, such as digits, punctuation, and whitespace, were left unchanged.

## Edge cases handled

* Empty string returns an empty string.
* Shift value of `0` leaves the input unchanged.
* Shift values greater than the alphabet length wrap correctly.
* Negative shift values wrap correctly.
* Uppercase and lowercase letters preserve their original case.
* Digits, punctuation, and whitespace remain unchanged.

## Anything special

I used `ALPHABET.len()` to satisfy the requirement of avoiding a hard-coded alphabet size. The `rem_euclid()` method correctly handles negative shifts, making the implementation simple and reliable. The algorithm runs in **O(n)** time, where `n` is the number of characters in the input, and returns a new `String`.
