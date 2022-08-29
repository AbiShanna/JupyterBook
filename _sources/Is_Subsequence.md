# Is Subsequence

Given two strings s and t, return true if s is a subsequence of t, or false otherwise.

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

Implementation:

```
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        if s == t or len(s) < 1:
            return True
        if len(t) < 1:
            return False
        if s[0] == t[0]:
            return self.isSubsequence(s[1:], t[1:])
        return self.isSubsequence(s, t[1:])
            
        
```

