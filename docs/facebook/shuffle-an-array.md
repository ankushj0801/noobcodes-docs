---
sidebar_position: 145
tags: [facebook]
---

# Shuffle an Array

### Problem Statement

Given an integer array nums, design an algorithm to randomly shuffle the array. All permutations of the array should be equally likely as a result of the shuffling.

Implement the Solution class:

- Solution(int[] nums) Initializes the object with the integer array nums.
- int[] reset() Resets the array to its original configuration and returns it.
- int[] shuffle() Returns a random shuffling of the array.

[Leetcode Link](https://leetcode.com/problems/shuffle-an-array)

#### Example 1:

```
Input
["Solution", "shuffle", "reset", "shuffle"]
[[[1, 2, 3]], [], [], []]
Output
[null, [3, 1, 2], [1, 2, 3], [1, 3, 2]]

Explanation
Solution solution = new Solution([1, 2, 3]);
solution.shuffle();    // Shuffle the array [1,2,3] and return its result.
                       // Any permutation of [1,2,3] must be equally likely to be returned.
                       // Example: return [3, 1, 2]
solution.reset();      // Resets the array back to its original configuration [1,2,3]. Return [1, 2, 3]
solution.shuffle();    // Returns the random shuffling of array [1,2,3]. Example: return [1, 3, 2]
```

#### Constraints:

- 1 <= nums.length <= 50
- -10<sup>6</sup> <= nums[i] <= 10<sup>6</sup>
- All the elements of nums are unique.
- At most 10<sup>4</sup> calls in total will be made to reset and shuffle.

### Code

```python title="Python"
class Solution:
    def __init__(self, nums):
        self.nums = nums[:]
        self.copy = nums[:]

    def reset(self):
        self.nums = self.copy[:]
        return self.nums

    def shuffle(self):
        n = len(self.nums)
        for i in range(n):
            j = randint(i, n - 1)
            self.nums[i], self.nums[j] = self.nums[j], self.nums[i]
        return self.nums
```
