# Longest-Subarray-With-Maximum-Bitwise-AND

You are given an integer array nums of size n.
Consider a non-empty subarray from nums that has the maximum possible bitwise AND.
In other words, let k be the maximum value of the bitwise AND of any subarray of nums. Then, only subarrays with a bitwise AND equal to k should be considered.
Return the length of the longest such subarray.
The bitwise AND of an array is the bitwise AND of all the numbers in it.
A subarray is a contiguous sequence of elements within an array.

class Solution:
    def longestSubarray(self, nums: List[int]) -> int:
        n=len(nums)
        maxLen, xMax, Len=0, 0, 0
        i=0
        while i<n:
            while i<n and nums[i]==xMax:
                i+=1
                Len+=1
            if i==n or nums[i]<xMax:
                maxLen=max(maxLen, Len)
                Len=0
            else:
                xMax=nums[i]
                maxLen=Len=1
            i+=1
        return maxLen
        
