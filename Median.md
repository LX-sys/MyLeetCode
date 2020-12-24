## 来源LeetCode

给定两个大小为 m 和 n 的正序（从小到大）数组 nums1 和 nums2。请你找出并返回这两个正序数组的中位数。

进阶：你能设计一个时间复杂度为 O(log (m+n)) 的算法解决此问题吗？
```
Eg1
输入：nums1 = [1,3], nums2 = [2]
输出：2.00000
解释：合并数组 = [1,2,3] ，中位数 2
```
```
Eg2
输入：nums1 = [1,2], nums2 = [3,4]
输出：2.50000
解释：合并数组 = [1,2,3,4] ，中位数 (2 + 3) / 2 = 2.5
```
```
Eg3
输入：nums1 = [0,0], nums2 = [0,0]
输出：0.00000
```
```
输入：nums1 = [], nums2 = [1]
输出：1.00000
```
```
输入：nums1 = [2], nums2 = []
输出：2.00000
```
```
提示
nums1.length == m
nums2.length == n
0 <= m <= 1000
0 <= n <= 1000
1 <= m + n <= 2000
-106 <= nums1[i], nums2[i] <= 106
```
### <font color=blue>代码</font>
```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        '''
          简单解法, 没有考虑时间复杂度
        '''
        
        temp = nums1+nums2
        arrlen = len(temp)

        if arrlen <= 1:
            return  temp[0] if temp else 0.0 
        
        # 排序
        temp.sort()
        
        # 下标
        index = arrlen//2

        # 判断奇偶
        if arrlen % 2 == 0:
            return float((temp[index]+temp[index-1])/2)
        else:
            return float(temp[index])
```








