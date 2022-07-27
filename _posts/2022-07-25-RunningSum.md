---
layout: post
title: Running Sum of 1d Array
---

Probably the easiest leetcode question out there. Let's start with an easy win.

# Problem Statement
1480. Running Sum of 1d Array

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

Example 1:

Input: nums = [1,2,3,4]
Output: [1,3,6,10]
Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

Example 2:

Input: nums = [1,1,1,1,1]
Output: [1,2,3,4,5]
Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].

Example 3:

Input: nums = [3,1,2,10,1]
Output: [3,4,6,16,17]

Constraints:

1 <= nums.length <= 1000
-10^6 <= nums[i] <= 10^6

# Planning
Welp. This is going to need a loop. I really racked my brain but I cannot think of any way to get around the O(n) time complexity here. 
Basically I am going to need to walk through the loop and update each element. 
Honestly it would be better from a debugging standard to make a new array and return that, instead of editing the array from the input. 
I would justify using a new array by:
- Python references can get tricky, if you don't know what you are doing you can acccidentally mutate the wrong reference

On the other hand, editing the array in place:
- Better space complexity O(1). Leetcode doesn't count the input variable so technically this takes no space? Regardless it is better than making a new array.

# Code
    class Solution(object):
        def runningSum(self, nums):
            """
            :type nums: List[int]
            :rtype: List[int]
            https://leetcode.com/problems/running-sum-of-1d-array/
            """
            # Set the rolling sum to zero
            rolling_sum = 0

            for index in range(0, len(nums)):
                # Get the current number
                current_number = nums[index]

                # Set the array value to the rolling sum
                nums[index] = rolling_sum + current_number

                # Set the new rolling sum
                rolling_sum = nums[index]

            return nums

# Testing
    if __name__ == '__main__':
        tempArray = [1, 2, 3, 4]
        sol = Solution()
        print(sol.runningSum(tempArray))

# Explaination
I think my code explains itself, if I did my job right. 
I could have done something fancier like, nums[i] += nums[i - 1], but I like the readability of my code. 
This question seems aimed at beginners so I wrote my code for beginners, the comments are pretty redundant unless you are new to python. 