# https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/description/


# Brute force 
1. we have to delte middle node
2. check edge cases correctly
3. then count node using  int count
4. then make variable middle = count / 2
5. and now delte it using extra variable

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
                        ListNode* deleteMiddle(ListNode* head) {
                         if (head == nullptr) return nullptr;    // if list is empty
   
                             if (head->next == nullptr) {  // if list contains only 1 node   this can lead to memory leak so for interview avoid this appraoch 
                           head = head-> next;
                             return head;
                            }
                             int count = 0;
                            ListNode* temp = head;
                            while (temp != nullptr) {
                                count++;
                                temp = temp->next;
                            }
                             int mid = count / 2;  
                             temp = head;
                            for (int i = 0; i < mid - 1; i++) {
                                temp = temp->next;
                            }
                             ListNode* toDelete = temp->next;
                            temp->next = toDelete->next;
                            delete toDelete;
                    
                            return head;
                        }
                    };











   <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<

                   class Solution {
        public:
            ListNode* deleteMiddle(ListNode* head) {
             if (head == nullptr) return nullptr;
                 if (head->next == nullptr) { // this approach is good
             return nullptr;
                }
                 int count = 0;
                ListNode* temp = head;
                while (temp != nullptr) {
                    count++;
                    temp = temp->next;
                }
                 int mid = count / 2;  
                 temp = head;
                for (int i = 0; i < mid - 1; i++) {
                    temp = temp->next;
                }
                 ListNode* toDelete = temp->next;
                temp->next = toDelete->next;
                delete toDelete;
        
                return head;
            }
        };



   time complexity : O(n) + O(n/2) = O(n)
space complexity : o(1)



  # brute force : 2

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
              ListNode* deleteMiddle(ListNode* head) {
                  if (head == nullptr) {
                      return nullptr;
                  }
                  if (head->next == nullptr) {
                      return nullptr;
                  }
          
                  ListNode* temp = head;
                  int count = 0;
                  while (temp != nullptr) {
                      count++;
                      temp = temp->next;
                  }
          
                  temp = head;
                  ListNode* prev = nullptr;
                  int mid = count / 2;
          
                  for (int i = 0; i <= mid - 1; i++) {
                      prev = temp;
                      temp = temp->next;
                  }
          
                  prev->next = temp->next;
                  return head;
              }
          };


   time complexity : O(n) + O(n/2) = O(n)
space complexity : o(1)



============================================================================
optimal approach 

       
