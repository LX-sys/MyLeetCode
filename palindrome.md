LeetCode题目


给定一个字符串 s，找到 s 中最长的回文子串。你可以假设 s 的最大长度为 1000。

eg1
```
输入: "babad"
输出: "bab"
注意: "aba" 也是一个有效答案。
```
eg2
```
输入: "cbbd"
输出: "bb"
```

My Code
```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
       
        if not s:
            return 
        elif s == s[::-1]:
            return s

        # 假设最大回文字符串
        maxLen = len(s)
        palindrome,palindromeIndex = [],[]
        index = 0
        # 简单些发，需要改进
        while index < maxLen:
            for i in range(len(s[index:])):   
                if not i:
                    temp = s[index:]
                else:
                    temp = s[index:-i]
                if temp == temp[::-1]:
                    palindrome.append(temp)
                    palindromeIndex.append(len(temp))
            index+=1
            
        if palindrome:
            return palindrome[palindromeIndex.index(max(palindromeIndex))]
        
        return s[0]
```
