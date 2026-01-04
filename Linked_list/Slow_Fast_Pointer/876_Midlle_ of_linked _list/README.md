
#  https://leetcode.com/problems/middle-of-the-linked-list/
## Brute force 

1. first count the node to find total number of node
2. use the mid variable to find middle element ( middle = count /2)
3. then run the loop from 0 to <mid
4. now u are about to get mid element as it will stop befor mid so loop will break
5. and u will be out of loop and u will get middle



        class Solution {
        public:
            ListNode* middleNode(ListNode* head) {
                if (head == NULL) return NULL; // empty list

        // Step 1: Count total nodes
        int count = 0;
        ListNode* temp = head;
        while (temp != NULL) {
            count++;
            temp = temp->next;
        }

        // Step 2: Find middle index
        int mid = count / 2;

        // Step 3: Traverse again to reach middle
        ListNode* curr = head;
        for (int i = 0; i < mid; i++) { // loop runs exactly mid times   o(n/2)
            curr = curr->next;
        }

        // Step 4: Return middle node
        return curr;
        }
        };

     ## time complexity : o(n) + o(n/2) = 0 (2n) = o(n);
    ## space complexity : o(1) as no space is used.

Confusion : how it will handle if ther will be one node ?
              ----> it will handle if node will be 1 / 2 == 0 so for loop won't run and it will send curr



===========================================================

## Optimal Approach: 

1. we will take 2 pointer named slow and fast
2. slow will move 1 step
3. fast will move 2 step
4. then we will return slow


        class Solution {
        public:
            ListNode* middleNode(ListNode* head) {
                if (head == NULL) return NULL; // handle empty list

        ListNode* slow = head;  // moves 1 step at a time
        ListNode* fast = head;  // moves 2 steps at a time

        // traverse until fast reaches the end
        while (fast != NULL && fast->next != NULL) {
            slow = slow->next;
            fast = fast->next->next;
        }

        // slow now points to the middle node
        return slow;
            }
        };


time complexity : o(n) 
space complexity : o(1)


