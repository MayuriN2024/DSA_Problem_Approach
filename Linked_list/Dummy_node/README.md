# Dummy Node

A dummy node (or sentinel node) is an extra node added at the start of a linked list.
Usually, its value doesn’t matter (can be 0, -1, or anything
Its next pointer points to the actual head


## mostly use for removing or deleting and merging 
ListNode* dummy = new ListNode(0, head);
or 
ListNode*  dummy = new ListNode( 0)
dummy -> next = head;
