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
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* _dummyhead = new ListNode(0,head);
        ListNode* cur = _dummyhead;
        int length = getListlength(head);
        for(int i = 1;i < length - n + 1;++i) {
            cur =cur->next;
        }
        cur->next = cur->next->next;
        ListNode* ans = _dummyhead->next;
        delete _dummyhead;
        return ans;
    }
    int getListlength(ListNode* Linkedlist) {
        int length = 0;
        while(Linkedlist != nullptr) {
            Linkedlist = Linkedlist->next;
            length++;
        }
        return length;
    }
};
```
