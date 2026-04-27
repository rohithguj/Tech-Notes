---
Created at: 2026-04-08
tags:
cssclasses:
Category:
  - "[[Unordered Map]]"
  - "[[DSA]]"
  - "[[Vector]]"
  - "[[2 pointer]]"
---
## Problem

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.


**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

## Approach

- Brute force approach two indented for loops
- Optimized approach is to use a [[hash map]]/[[Unordered Map]] to map the value of index with the key as (target  - current index) 



## Learnings

- **When using a hash always check the map first and then update to avoid self reference:**
	**Iteration 1 (i = 0):**
	1. *Your current number nums[0] is 3.*
	2. *You calculate val = 6 - 3, so val is 3.*
	3. *val > 0 is true, so you insert it into your map: map[3] = 0. (Your "wanted poster" is up: looking for a 3!)*
	4. *The Bug Happens Here: On the very next line, you check if nums[i] (which is 3) is inside the map.*
	5. *Because you just put it there on step 3, the map says "Yes, I have a 3!"*
	6. *Your code immediately returns {map[3], 0}, which evaluates to [0, 0].*
	7. *The code completely stops at the very first number because 3 + 3 = 6, and it accidentally matched the first 3 with itself.*

- [[Unordered Map]]

## Code

```
class Solution {

public:

    vector<int> twoSum(vector<int>& nums, int target) {

        int len = nums.size();

        vector<int> res (2);

        unordered_map<int, int> map;

        for (int i=0; i< len; i++) {

            if ( map.find(nums[i]) != map.end() ) {

                return (vector<int> {map[nums[i]], i} ) ;

            }

            int val = target - nums[i];

            map[val] = i;

        }

        return (vector<int> {0,0});

    }

};
```



