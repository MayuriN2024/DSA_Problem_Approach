# WHAT IS THE SLOW & FAST POINTER PATTERN?

# We use two pointers on the same linked list:

# Slow pointer → moves 1 step

# Fast pointer → moves 2 steps



## template
      ListNode* slow = head;
      ListNode* fast = head;
      
      while (fast != NULL && fast->next != NULL) {
          slow = slow->next;
          fast = fast->next->next;
      }



-----------------------------------------------------

4️⃣ ALL IMPORTANT QUESTIONS (WITH LINKS)

Below is EVERY IMPORTANT QUESTION that uses slow & fast pointers.

🔹 A. FINDING MIDDLE / POSITION
1. Middle of Linked List

👉 Why: fast reaches end → slow at middle
🔗 https://leetcode.com/problems/middle-of-the-linked-list/

2. Delete Middle Node

👉 Why: slow tracks middle, fast tracks end
🔗 https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/

3. Split Linked List into Two Halves

👉 Why: slow stops at mid
🔗 https://www.geeksforgeeks.org/split-a-circular-linked-list-into-two-halves/

🔹 B. CYCLE / LOOP PROBLEMS (MOST IMPORTANT)
4. Detect Cycle (Floyd’s Algorithm)

👉 Why: fast catches slow if cycle exists
🔗 https://leetcode.com/problems/linked-list-cycle/

5. Find Start of Cycle

👉 Why: distance math property
🔗 https://leetcode.com/problems/linked-list-cycle-ii/

6. Remove Cycle

👉 Why: break last node of loop
🔗 https://www.geeksforgeeks.org/remove-loop-in-linked-list/

7. Length of Cycle

👉 Why: move pointer inside loop
🔗 https://www.geeksforgeeks.org/find-length-of-loop-in-linked-list/

8. Check Circular Linked List

👉 Why: fast reaches head again
🔗 https://www.geeksforgeeks.org/check-if-a-linked-list-is-circular-linked-list/

🔹 C. PALINDROME / COMPARISON
9. Palindrome Linked List

👉 Why: find middle + reverse second half
🔗 https://leetcode.com/problems/palindrome-linked-list/

10. Reorder List

👉 Why: split at middle
🔗 https://leetcode.com/problems/reorder-list/

🔹 D. MATH + NON-LINKED LIST USES (IMPORTANT)
11. Happy Number

👉 Why: cycle detection in numbers
🔗 https://leetcode.com/problems/happy-number/

12. Find Duplicate Number

👉 Why: array treated as linked list
🔗 https://leetcode.com/problems/find-the-duplicate-number/

13. Circular Array Loop

👉 Why: fast & slow detect cycle
🔗 https://leetcode.com/problems/circular-array-loop/

🔹 E. ADVANCED / INTERVIEW FAVORITES
14. Intersection of Two Linked Lists (Variant)

👉 Why: equalize distance
🔗 https://leetcode.com/problems/intersection-of-two-linked-lists/

15. Find Middle of Circular Linked List

👉 Why: fast hits head again
🔗 https://www.geeksforgeeks.org/find-middle-of-circular-linked-list/
