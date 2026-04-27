---
Created at: 2026-04-09
tags:
Category:
  - "[[Unordered Set]]"
  - "[[DSA]]"
---
## Problem

Given an integer array `nums` and an integer `k`, return `true` _if there are two **distinct indices**_ `i` _and_ `j` _in the array such that_ `nums[i] == nums[j]` _and_ `abs(i - j) <= k`.

**Example 1:**

**Input:** nums = [1,2,3,1], k = 3
**Output:** true

**Example 2:**

**Input:** nums = [1,0,1,1], k = 1
**Output:** true

**Example 3:**

**Input:** nums = [1,2,3,1,2,3], k = 2
**Output:** false

## Approach

need to only parse and keep a certain window in the memory so we use a set to keep k context and then pop as we move forward and then check for duplicates insert the new element

## Learnings

[[Unordered Set]]

## Code




