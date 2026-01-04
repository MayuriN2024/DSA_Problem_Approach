# https://leetcode.com/problems/merge-two-sorted-lists/description/
#optimal 

its dummy list where we make a dummy list to store the two list and then we merge it 
      
      class Solution {
      public:
          ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
             ListNode* temp = new ListNode();
             ListNode* curr = temp;
      
             while( list1 != NULL && list2 != NULL){
              if( list1 -> val <= list2-> val){
                  curr -> next = list1;
                list1 = list1->next;
              }
              else{
              curr -> next = list2;
              list2 = list2 -> next;
             }
      
             curr = curr -> next;
             }
             if( list1 != NULL){
               curr -> next = list1;
             }
      
      
             if( list2 != NULL){
               curr -> next = list2;
              
             }
      
      
      
       return temp->next;
          }
      };
      
  ## time complexity : o(m) + o(n)  = o(m+n) 
  ## space complexity : o(m+n);
  =======================================================

  # brute force usine vector 

          class Solution {
        public:
            ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
                ListNode * temp1 = list1;
                ListNode * temp2 = list2;
                vector<int>result;
        
                while( temp1 != NULL ){
                    result.push_back( temp1->val);
                    temp1 = temp1->next;
                   
                }
        
                while( temp2 != NULL ){
                    result.push_back( temp2->val);
                    temp2 = temp2->next;
                   
                }
                sort(result.begin(), result.end());
                ListNode* dummy = new ListNode(0);
                ListNode * current = dummy;
        
                for( int val : result){
                        current-> next  =new ListNode(val);
                        current = current -> next;
                }
                
                return dummy-> next;
        
            }
        };
        View less
         
        
  Step	Complexity
Copy list1	O(n)
Copy list2	O(m)
Sort vector	O((n + m) log(n + m))
Build list	O(n + m)

Total:

O(n+m+(n+m)log(n+m)+n+m)=O((n+m)log(n+m))

So the dominant term is the sort, which is O((n + m) log(n + m)).  



Space complexity: O(n + m)
