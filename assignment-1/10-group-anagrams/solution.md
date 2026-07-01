# Solution notes: Group anagrams

## Approach

I used a `HashMap<String, Vec<String>>` to group words by a common signature. For each word, I first converted it to lowercase to make the comparison case-insensitive. I then collected its characters into a vector, sorted them, and converted the sorted characters back into a `String`. This sorted string served as the key for the hash map.

The original word, with its original casing preserved, was cloned and added to the corresponding group. After processing all words, I collected the groups from the hash map into a `Vec<Vec<String>>`.

## Edge cases handled

* Empty input returns an empty vector.
* A single word forms its own group.
* Words that differ only in letter case are grouped together.
* The original order of words is preserved within each anagram group.

## Anything special

The sorted lowercase characters provide a unique signature for each anagram group. I used `sort_unstable()` because stability is not required when sorting the characters. Building the signature takes **O(k log k)** time for a word of length `k`, and the overall solution groups words efficiently using a `HashMap`.
