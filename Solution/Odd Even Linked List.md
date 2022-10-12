``` C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) {
        if(head == nullptr) {
            return nullptr;
        }
        ListNode* evenHead = head->next;
        ListNode* oddHead = head;
        ListNode* even = evenHead; // copy
        while(even != nullptr && even->next != nullptr) {
            oddHead->next = even->next;
            oddHead = oddHead->next; //oddHead 变成 even 的后一个节点
            even->next = oddHead->next;
            even = even->next;
        }
        oddHead->next = evenHead;
        return head;
    }
};
```
