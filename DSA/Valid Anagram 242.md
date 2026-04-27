---
Created at: 2026-04-27
tags:
Category:
  - "[[Learnings]]"
  - "[[frequency]]"
  - "[[DSA]]"
---
## Problem

Given two strings s and t, return true if t is an anagram of s, and false otherwise.


Example 1:

Input: s = "anagram", t = "nagaram"

Output: true

Example 2:

Input: s = "rat", t = "car"

Output: false

 

Constraints:

1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.

## Approach

- The Idea is to build a frequency of each characters appearance and check if frequency is matching

- **Approach 1:** ^18aa21
	- Planned on building one parse loop where I added a increase and decrease for both the diff strings.
	- Then parse on string check for frequency = 0
	- **The issue is also we have a failure not tracked until both the strings are completely parsed**.

- **Approach 2:**
	- The Idea is we use the first loop to only add.
	- Then we have the second parse loop where we subtract if value hits negative then we happen to return false
	- The advantage is that we detect issue early on saving on some time. Time optimized compared to Approach 1. [[#^18aa21]]

- ==**Note**:==
	- The though was to use a hash map for characters but has assign unknow size and then adds more memory as needed.
	- So we use a 26 length array because the number alphabets is only 26.
	- Adding the size not same condition is a more optimized approach of finding issues earlier.

## Learnings

- While trying to count frequencies of a string we can use '**current value - a**' to get the int since the vector or array only can have number as index and cant take char to count the frequency.

## Code

```
class Solution {
public:
    bool isAnagram(string s, string t) {
        // Early exit: If lengths don't match, it's impossible
        if (s.size() != t.size()) {
            return false;
        } 
        
        // O(1) Space Optimization: Array instead of Hash Map
        int freq[26] = {0}; 
        
        // Loop 1: Deposit Only
        for (int i = 0; i < s.size(); i++) {
            freq[s[i] - 'a']++;
        }
        
        // Loop 2: Withdrawal Only
        for (int i = 0; i < t.size(); i++) {
            freq[t[i] - 'a']--;
            
            // The Fail-Fast Check
            if (freq[t[i] - 'a'] < 0) {
                return false;
            }
        }
        
        // If we survived Loop 2 without going negative, it's a perfect match!
        return true;
    }
};
```




