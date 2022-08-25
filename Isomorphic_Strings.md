# Isomorphic Strings

Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.
All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

Implementation:

```
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        print(list(zip(s,t)))
        if len(s) != len(t):
            return False
        if s == t:
            return True
        res = {}
        for i in range(len(s)):
            if s[i] not in res:
                if t[i] in res.values():
                    return False
                res[s[i]] = t[i]
            elif res[s[i]] != t[i]:
                return False
        return True
                    
```

