```C++
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        // 要插入的时候定义一个虚拟头节点, 就不需要特判第一个点了
        //使用预先指针的目的在于链表初始化时无可用节点值，而且链表构造过程需要指针移动，进而会导致头指针丢失，无法返回结果
        auto dummy = new ListNode(-1), cur = dummy;  
        //cur 表示 sum链表的尾结点
        int t = 0;
        while (l1 || l2 || t) {
            if (l1) {
                t += l1->val, l1 = l1->next;
            }
            if (l2) {
                t += l2->val, l2 = l2->next;
            }
            cur = (cur->next = new ListNode(t % 10));
            t /= 10;
        }
        return dummy->next; // 真正的链表头结点
    }
};
```
