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
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        unordered_set<ListNode*> table;
        while(headA != nullptr) {
            table.insert(headA);
            headA = headA->next;
        }
        while(headB != nullptr) {
            if(table.count(headB)) {
                return headB;
            }
            headB = headB->next;
        }
        return nullptr;
    }
};
```
### Solution 2 
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
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        int lengthA = checkLength(headA);
        int lengthB = checkLength(headB);
        while(lengthA != lengthB) {
            if(lengthA > lengthB) {
                headA = headA->next;
                lengthA--;
            }
            else {
                headB = headB->next;
                lengthB--;
            }
        }
        while(headA != headB) {
            headA = headA->next;
            headB = headB->next;
        }
        return headA;
    }
    int checkLength(ListNode* list) {
        int length = 0;
        while(list != nullptr) {
            length++;
            list = list->next;
        }
        return length;
    }
};
```
