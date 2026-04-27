---
Created at: 2026-04-27
tags:
Category:
  - "[[Learnings]]"
  - "[[Unordered Map]]"
  - "[[Prefix sum + Hash]]"
---
## Problem

Given an array of integers `nums` and an integer `k`, return _the total number of subarrays whose sum equals to_ `k`.

A subarray is a contiguous **non-empty** sequence of elements within an array.

**Example 1:**

**Input:** nums = [1,1,1], k = 2
**Output:** 2

**Example 2:**

**Input:** nums = [1,2,3], k = 3
**Output:** 2

**Constraints:**

- `1 <= nums.length <= 2 * 104`
- `-1000 <= nums[i] <= 1000`
- `-107 <= k <= 107`

## Approach

- Two pointer approaches fail here because the array is not sorted so negetive numbers are possible breaking the two pointer logic to move right as long as sum is less than k.
- The idea is we carry a cumulative sum which adds all the values write to a map so that when we hit k - cum sum at some point we take the first index and last so we get all the sub arrays.


## Learnings

- Always remember to add a base condition because when we cumulative 0 we know we started at the first index.

## Code

```
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        unordered_map<int, int> look;
        
        look[0] = 1; 
        
        int sum = 0;
        int count = 0;

        for (int num : nums) { 
            sum = sum + num;
            int target = sum - k;
            
            if (look.find(target) != look.end()) {
                count = count + look[target];
            }
            
            look[sum]++;
        }
        
        return count;
    }
};
```


