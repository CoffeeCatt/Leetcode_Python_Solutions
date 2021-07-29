## Problem
https://leetcode.com/problems/longest-substring-without-repeating-characters/
```
Given a string s, find the length of the longest substring without repeating characters.
```

## Code
```
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        max_count=0
        j=0
        start=0
        seen=dict()
        while j<len(s):
            if s[j] not in seen:
                seen[s[j]]=j
            else:
                last_seen=seen[s[j]]
                seen[s[j]]=j
                start=max(last_seen+1,start)
            max_count=max(max_count,(j-start+1))
            j+=1
        return max_count
```
# Complexity
- Time complexity : O(n). Index j will iterate n times.

- Space complexity (HashMap) : O(min(m, n)). 
