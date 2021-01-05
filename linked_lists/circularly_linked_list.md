---
source:https://en.wikipedia.org/wiki/Linked_list
---
What is a circular linked list?
<!--question-->
In the last node of a list, the link field often contains a null reference, a special value is used to indicate the lack of further nodes. A less common convention is to make it point to the first node of the list; in that case, the list is said to be 'circular' or 'circularly linked'; otherwise, it is said to be 'open' or 'linear'. It is a list where the last pointer points to the first node.

![Circularly linked list](images/Singly-linked-list.svg/700px-Circularly-linked-list.svg.png)

In the case of a circular doubly linked list, the first node also points to the last node of the list.
