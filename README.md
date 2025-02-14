[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/KjM8uJt0)
1. Aim:
To implement the concept of Linked List by solving the problems on LeetCode. 
i. Print Linked list
ii. Remove duplicates from a sorted list
iii. Reverse a linked list
iv. Delete middle node of a list
2. Objective: 
• Traverse and display all elements of the linked list.
• Remove consecutive duplicate values to retain unique elements.
• Reverse the order of nodes by modifying pointers.
• Identify and remove the middle node efficiently.
3. Code:
Problem 1: Print linked list
class Solution {
public:
 // Function to display the elements of a linked list in same line
 void printList(Node *head) {
 Node*temp=head;
 while(temp!=NULL){
 cout<<temp->data<<" ";
 temp=temp->next;
 }
 }
};
Problem 2: Remove Duplicates from Sorted List
class Solution {
public:
ListNode* deleteDuplicates(ListNode* head) {
if(!head) return nullptr;
ListNode*current=head;
while(current->next){
if(current->val==current->next->val){
ListNode*temp=current->next;
current->next=current->next->next;
delete temp;
}else{
current=current->next;
}
}
return head;
}
};
Problem 3: Reverse Linked List
class Solution {
public:
ListNode* reverseList(ListNode* head) {
ListNode*prev=nullptr;
ListNode*current=head;
ListNode*next=nullptr;
while(current!=nullptr){
next=current->next;
current->next=prev;
prev=current;
current=next;
}
return prev;
}
};
Problem 4: Delete the Middle Node of a Linked List
class Solution {
public:
ListNode* deleteMiddle(ListNode* head) {
if (!head || !head->next) // If list is empty or has only one node
return nullptr;
ListNode *slow = head, *fast = head, *prev = nullptr;
// Move fast pointer twice as fast as slow pointer
while (fast && fast->next) {
prev = slow;
slow = slow->next;
fast = fast->next->next;
}
// Remove the middle node
if (prev)
prev->next = slow->next;
delete slow; // Free memory
return head;
}
};
