# https://leetcode.com/problems/remove-nth-node-from-end-of-list/
## Brute force 

1. we have given n
2. so we can count toatal node and then substract count from that
3. and run the node as we have to delete from last so (count - n -1) is imp
4. run the loop and delte 


           class Solution {
          public:
              ListNode* removeNthFromEnd(ListNode* head, int n) {
                  if (head == NULL) return NULL;

        int count = 0;
        ListNode* temp = head;

        // Count length
        while (temp != NULL) {
            count++;
            temp = temp->next;
        }

        // If head needs to be deleted
        if (n == count) {
            ListNode* del = head;
            head = head->next;
            delete del;
            return head;
        }

        // Go to node before the one to delete
        temp = head;
        for (int i = 0; i < count - n - 1; i++) {          -1 is crucial 
            temp = temp->next;
        }

        ListNode* delnode = temp->next;
        temp->next = delnode->next;
        delete delnode;

        return head;
    }
        };
# time complexity : o(n) 
# space complexity : o(1)


-------------------------------------------------------------


# optimal solution using dummy

1. we will use dummy as we have not take care of edge case


        /**
         
        public:
            ListNode* removeNthFromEnd(ListNode* head, int n) {
                ListNode* dummy = new ListNode(0);
                dummy -> next = head;

        ListNode* temp = head;
        int count = 0;
        while( temp != NULL){
            count++;
            temp = temp -> next;
        } 

        ListNode*  current = dummy;
        int total = count - n;
        while( total > 0){
            current = current -> next;
            total--;
        }

        current -> next = current-> next -> next;
        return dummy -> next;
    }
      };

  time complexity : o(n) 
  space complexity : o(1)


