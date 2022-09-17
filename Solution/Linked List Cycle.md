``` C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if(head == nullptr || head->next == nullptr) {
            return false;
        }
        ListNode* f = head, *s = head;
        while(f && f->next) {
            s = s->next;
            f = f->next->next;
            if(s == f) {
                return true;
            }
        }
        return false;
    }
};
```
