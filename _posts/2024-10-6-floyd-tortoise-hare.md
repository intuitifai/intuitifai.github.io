---
layout: post
title: Floyd's Cycle Detection Algorithm
---

<center><img width="308" alt="image" src="https://github.com/user-attachments/assets/8bda530c-f8aa-4405-848b-51ac0c5b2693"></center>

Today, we are going to discuss an optimal algorithm used to find a loop in a linked list. **Floyd's Cycle Detection Algorithm**, also known as the "Tortoise and Hare" algorithm, can detect cycles in linked lists or arrays (we will focus on linked lists today). This algorithm uses two pointers moving at different speeds to detect the presence of a cycle.

## How Does It Work?

1. **Two Pointers:** The algorithm uses two pointers:
   * `slow` (tortoise) moves one step at a time.
   * `fast` (hare) moves two steps at a time.

2. **Cycle Detection:** 
   * If there is **no cycle**, the `fast` pointer will eventually reach the end of the list.
   * If there **is a cycle**, the `fast` and `slow` pointers will eventually meet inside the cycle.

### Finding the Start of the Cycle

To find the exact node where the cycle begins:
1. Set one pointer to the head of the list.
2. Move both pointers one step at a time until they meet again.
3. The meeting point is the **start of the cycle**.

### Example to Understand the Concept

Let's consider a singly linked list with nodes `[1, 2, 3, 4]`. As shown in the image, there is a cycle present in the linked list.

<center><img width="479" alt="image" src="https://github.com/user-attachments/assets/22dc639d-6c3f-4063-b150-1c44e84f8443"></center>

We place two pointers, `tortoise` and `hare`, which will move at different speeds (`slow` and `fast`, respectively).

- Images here illustrate the movement of the two pointers:
<center><img width="443" alt="image" src="https://github.com/user-attachments/assets/71698561-ef6e-4fa6-92eb-5f7b2ff303b3"></center>
<center><img width="446" alt="image" src="https://github.com/user-attachments/assets/c4aaf34f-4492-4205-bc03-a23e3f070383"></center>
<center><img width="442" alt="image" src="https://github.com/user-attachments/assets/e90ce48b-a4c4-428d-9026-e57fb58831f0"></center>
<center><img width="550" alt="image" src="https://github.com/user-attachments/assets/d7861e52-db0c-4700-8b49-be869addce20"></center>

## Code in Python

```python
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
