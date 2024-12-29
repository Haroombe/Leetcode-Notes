<hr>

2024-12-29 10:47

Status:

Tags: [[leetcode]], [[LinkedList]]

<hr>

# 19. Remove Nth node from the end of the list

## Problem overview

Given the head of a linked list, return back the linked list with the nth from the back node removed.

EX: 

1 -> 2 -> 3 -> 4 -> 5 -> X
remove the 2nd from the last node.
1 -> 2 -> 3 -> 5 -> X

### Naive solution

We can use two pointers, one slow and one fast. Fast will move at double speed and essentially find the length.  The slow pointer will keep its own length and move at one speed. When the fast pointer reaches the end we can use the length - n  to figure out how much further slow pointer needs to go before removing the next node.
EX: (from above)
len = 5
5 - 2 = 3
travel to the 3rd node and remove the next one.

Note: is this considered one pass?


### Actual solution

Use two pointers, but keep a gap of n with trailing slow. the slow will be actually n -1 behind so we can remove the next node so we use a dummy.next = head as the initial node for slow.

So we iterate fast n times. 
Then we have two cases. We know there are atleast n nodes, so
1. we are passed the last node, meaning the head is to be removed
2. we are not passed the last node, meaning the head is not to be removed

if 1. -> we can just skip over head and return head.next

if 2. 
dummy -> 1 -> 2 -> 3 -> 4 -> 5 -> X
                 L                       R
Iterate until the fast pointer is None. This places slow right before the node to replace. remove and return



# References
[problem](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

[MyCode](https://leetcode.com/problems/remove-nth-node-from-end-of-list/solutions/6202281/haroombe-sol-by-haroombe-nhlt)