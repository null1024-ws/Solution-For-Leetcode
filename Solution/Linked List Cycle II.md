### Solution 1 Hash Table
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
    ListNode *detectCycle(ListNode *head) {
        unordered_set<ListNode *> table;
        while (head != nullptr) {
            if (table.count(head)) {
                return head;
            }
            table.insert(head);
            head = head->next;
        }
        return nullptr;
    }
};
```
Solution 2 Two Pointers
``` C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution{
public:
    ListNode *detectCycle(ListNode *head){
        ListNode *slow = head, *fast = head;
        while(fast && fast->next){
            slow = slow->next;
            fast = fast->next->next;
            if(slow==fast) {
                break;
            }
        }
        if(!fast || !fast->next) {
            return nullptr;
        }
        fast = head;
        while(fast != slow){
            if(!fast || !fast->next) {
                return nullptr;
            }
            slow = slow->next;
            fast = fast->next;
        }
        return fast;
    }
};
```
