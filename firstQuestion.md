# MyLeetCode
LeetCode Result




题目:
给出两个 非空 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 逆序 的方式存储的，并且它们的每个节点只能存储 一位 数字。

如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。

您可以假设除了数字 0 之外，这两个数都不会以 0 开头。

输入：(2 -> 4 -> 3) + (5 -> 6 -> 4)
输出：7 -> 0 -> 8
原因：342 + 465 = 807
--------------------------
个人解答(python3)

# Definition for singly-linked list.
```python

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
    
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
 
        head = ListNode()
        s = head
        a,b,carry= 0,0,0
        while(l1 or l2):
            if l1:
                a = l1.val
                l1 = l1.next
            else:  # 0补位
                a = 0
            
            if l2:
                b = l2.val
                l2 = l2.next
            else:
                b = 0
            
            # 结果 = a+b+进位数字
            data = a+b+carry
            # 判断是否有进位
            carry = data//10
            if carry:
                # 结果取个位
                s.next=ListNode(data%10)
            else:
                s.next=ListNode(data)
            s = s.next
        
        # 如果有进位,添加一个节点
        if carry:
            s.next = ListNode(1)

        
        return head.next
     
```
