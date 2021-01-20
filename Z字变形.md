LeetCode

将一个给定字符串 s 根据给定的行数 numRows ，以从上往下、从左到右进行 Z 字形排列。

比如输入字符串为 "PAYPALISHIRING" 行数为 3 时，排列如下

'''
P   A   H   N
A P L S I I G
Y   I   R
'''
之后，你的输出需要从左往右逐行读取，产生出一个新的字符串，比如："PAHNAPLSIIGYIR"。

Eg1
```
输入：s = "PAYPALISHIRING", numRows = 3
输出："PAHNAPLSIIGYIR"
```
Eg2:
```
输入：s = "PAYPALISHIRING", numRows = 4
输出："PINALSIGYAHRPI"
解释：
P     I    N
A   L S  I G
Y A   H R
P     I
```
Eg3:
```
输入：s = "A", numRows = 1
输出："A"
```

MY Code
```python
class Solution:
    def convert(self, s: str, numRows: int) -> str:
        if numRows<2:
            return s

        reStr = ["" for i in range(numRows+1)]
        flag = True
        # 最大索引值,当前索引值
        maxIndex,indexIng = numRows-1,-1
        
        for s_str in s:
            if indexIng < maxIndex and flag:
                indexIng+=1
                reStr[indexIng]+=s_str
            else:
                if flag:
                    flag = False
                indexIng-=1
                reStr[indexIng]+=s_str
                if indexIng == 0:
                    flag = True
                
        return "".join(reStr)
```

结果
```
执行用时：
60 ms
, 在所有 Python3 提交中击败了
78.90%
的用户
内存消耗：
15.1 MB
, 在所有 Python3 提交中击败了
14.49%
的用户
```

