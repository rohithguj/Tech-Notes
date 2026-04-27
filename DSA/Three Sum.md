---
Created at: 2026-04-10
tags:
Category:
  - "[[2 pointer]]"
  - "[[Vector]]"
---
## Problem

Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

**Example 1:**

**Input:** nums = [-1,0,1,2,-1,-4]
**Output:** [[-1,-1,2],[-1,0,1]]
**Explanation:** 
nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
The distinct triplets are [-1,0,1] and [-1,-1,2].
Notice that the order of the output and the order of the triplets does not matter.

**Example 2:**

**Input:** nums = [0,1,1]
**Output:** []
**Explanation:** The only possible triplet does not sum up to 0.

**Example 3:**

**Input:** nums = [0,0,0]
**Output:** [[0,0,0]]
**Explanation:** The only possible triplet sums up to 0.

## Approach

- Sort the array first
- Then pick one number and to find the remaining two just follow logic like [[Two Sum]].
- check the sum of two pointers plus locked and if high decrease the end pointer if les increase the start pointer.
- Similar logic for [[Four Sum]] just two locks.

## Learnings



## Code


### Failed Code

The reason for this fail is trying to handle everything and maipula5ting pointers in one while loop left few cases cause issue. 
```
class Solution {

public:

    vector<vector<int>> threeSum(vector<int>& nums) {

        sort(nums.begin(), nums.end());

        int start = 0;

        int end = nums.size()-1;

        for (int i = 0 ; i<= end; i++) {

            cout << nums[i];

        }

        cout << endl;

        unordered_map <int, int> look;

        vector <vector <int>> res;

        while ((start < end || nums[start] + nums[end] > 0 ) && end >=2) {

            if (look.find(nums[start]) != look.end()) {

                // cout<<"found" << look[nums[start]];

                // cout<< endl;

                if (find(res.begin(), res.end(), vector <int> {nums[end], nums[start], look[nums[start]]}) == res.end()){

                    res.push_back(vector<int> {nums[end], nums[start], look[nums[start]]});

                }      

                // look.clear();

            }

            int need =  - (nums[end] + nums[start]);

            look[need] = nums[start];

            // cout << nums[start] << "    " << nums[end];

            // cout << endl;

            // cout<< need;

            // cout<<endl;

            if (start == end-1 || nums[start] > 0) {

                start = -1;

                end --;

                // cout<<"tring";

                look.clear();

            }

            start ++;

        }

        return (res);

    }

};
```




