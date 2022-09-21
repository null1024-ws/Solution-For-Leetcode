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
    ListNode* removeElements(ListNode* head, int val) {
        ListNode* node = new ListNode(val);
        ListNode* _dummy = new ListNode(0, head);
        ListNode* temp = _dummy;
        while(temp->next != nullptr) {
            if(temp->next->val == val) {
                temp->next = temp->next->next;
            }
            else temp = temp->next;
        }
        return _dummy->next;
    }
};
```
