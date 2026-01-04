


## You want the nth node from the end of a linked list.

You have two runners:
Fast pointer (leader)
Slow pointer (follower)
If fast runs n steps ahead, slow can start following.
When fast reaches the finish line (NULL), slow is exactly at the node you care about.
Key: The gap = distance from slow to target node.


3️⃣ Why the gap works

Fast pointer goes n steps ahead → now slow is “n behind” fast.
Moving them together keeps this gap constant.
Fast reaching the end = slow has moved exactly enough to reach the target node.
No need to count the length of the list! ✅


# https://leetcode.com/problems/remove-nth-node-from-end-of-list/

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
      
      ListNode* removeNthFromEnd(ListNode* head, int n) {
          // Step 0: Add dummy node to handle edge cases (like removing head)
          ListNode* dummy = new ListNode(0);
          dummy->next = head;
    
    ListNode* slow = dummy;
    ListNode* fast = dummy;

    // Step 1: Move fast n+1 steps ahead to create gap
    for (int i = 0; i <= n; i++) {
        fast = fast->next;
    }

    // Step 2: Move both pointers together until fast reaches end
    while (fast != nullptr) {
        slow = slow->next;
        fast = fast->next;
    }

    // Step 3: Slow is just before the target node; remove it
    ListNode* toDelete = slow->next;
    slow->next = slow->next->next;
    delete toDelete; // free memory

    // Step 4: Return new head
    return dummy->next;
        }

