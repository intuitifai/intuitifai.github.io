---
layout: post
title: Floyd's Cycle Detection Algorithm
---
<center><img width="308" alt="image" src="https://github.com/user-attachments/assets/8bda530c-f8aa-4405-848b-51ac0c5b2693"></center>

Today, we are going to talk about a very optimal algorithm that can be used to find a loop in a linked list. 
**Floyd's Cycle Detection Algorithm**, also known as the "Tortoise and Hare" algorithm, is used to detect a cycle in a linked list or array (we will be looking into Linked list for today).
The algorithm uses two pointers moving at different speeds to detect the presence of a cycle.

## How it works?
1. Two pointers: The algorithm uses two pointers:
  * `slow` (tortoise) which moves one step at a time
  * `fast` (hare) which moves two steps at a time
2. Cycle detection:
  * If there is no cycle, the `fast` pointer will eventually reach the end of the list.
  * If there is a cycle, at some point, both the `fast` and `slow` pointers will meet inside the cycle
### Start of the cycle
To find the exact node where the cycle begins, set one pointer to the head of the list and move both the pointers one step at a time, until they meet again.
The meeting point is the `start of the cycle`.

Lets understand the concept with an example. Lets say we have a singly linked list with nodes as `[1, 2, 3, 4]`. We can see from the image that there is a cycle present in the linked list.

<center><img width="479" alt="image" src="https://github.com/user-attachments/assets/22dc639d-6c3f-4063-b150-1c44e84f8443"></center>

We can place two pointers, `tortoise` and `hare`, which will move `slow` and `fast` respectively.
<img width="443" alt="image" src="https://github.com/user-attachments/assets/71698561-ef6e-4fa6-92eb-5f7b2ff303b3">
<img width="446" alt="image" src="https://github.com/user-attachments/assets/c4aaf34f-4492-4205-bc03-a23e3f070383">
<img width="442" alt="image" src="https://github.com/user-attachments/assets/e90ce48b-a4c4-428d-9026-e57fb58831f0">
<img width="550" alt="image" src="https://github.com/user-attachments/assets/d7861e52-db0c-4700-8b49-be869addce20">

## Code in Python
```
class ListNode:
    def __init__(self, value=0, next=None):
        self.value = value
        self.next = next

def has_cycle(head):
    slow = head
    fast = head

    while fast is not None and fast.next is not None:
        slow = slow.next 
        fast = fast.next.next
        
        # Check if the slow and fast pointers meet
        if slow == fast:
            return True  # Cycle detected

    return False  # No cycle

# Example Usage
# Creating a cycle for demonstration
node1 = ListNode(3)
node2 = ListNode(2)
node3 = ListNode(0)
node4 = ListNode(-4)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node2  # Creates a cycle linking back to node2

print(has_cycle(node1))  # Output: True
```




