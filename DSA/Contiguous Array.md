---
Created at: 2026-04-27
tags:
Category:
  - "[[Learnings]]"
  - "[[Unordered Map]]"
  - "[[Prefix sum + Hash]]"
---
## Problem

Given a binary array `nums`, return _the maximum length of a contiguous subarray with an equal number of_ `0` _and_ `1`.

**Example 1:**

**Input:** nums = [0,1]
**Output:** 2
**Explanation:** [0, 1] is the longest contiguous subarray with an equal number of 0 and 1.

**Example 2:**

**Input:** nums = [0,1,0]
**Output:** 2
**Explanation:** [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.

**Example 3:**

**Input:** nums = [0,1,1,1,1,1,0,0,0]
**Output:** 6
**Explanation:** [1,1,1,0,0,0] is the longest contiguous subarray with equal number of 0 and 1.

**Constraints:**

- `1 <= nums.length <= 105`
- `nums[i]` is either `0` or `1`.


## Approach

- This is similar to the [[Subarray Sum Equals K]]. The idea is that we use the 0 as -1 check where we have the sum is 0 so we get the first index.

- In frequency based prblems always add a base case which here is starting with -1 because if 0 is not present in the start when we hit first 0 since 0 is not there we will not note the index and miss the first subaaray.

- Gemini :
	- If you don't include `idx[0] = -1`, your algorithm becomes completely blind to any valid subarray that starts at the very beginning (Index 0) of your array.
## Learnings



## Code
```
class Solution {
public:
    int findMaxLength(vector<int>& nums) {
        int len = 0;
        int m = 0;
        int curr = 0;
        unordered_map <int, int> idx;
        idx[0] = -1;
        // vector <int> arr;
        for (int i = 0; i< nums.size(); i++) {
            int rand;
            rand = nums[i]==1 ? curr +1 : curr-1;
            
            // look[i] = rand;
            curr = rand;
            if(idx.find(curr) != idx.end()) {
                m = max(m, i-idx[curr]);
                idx[rand] = min(i, idx[rand]);
            } else {
                idx[rand] = i;
            }
            // arr[i] = nums[i]==1 ? arr[i-1] +1 : arr[i-1]-1;
        }
        // for (int i = 0; i< nums.size(); i++) {
            // if (arr[i])
        // }
        return (m);
    }
};
```



