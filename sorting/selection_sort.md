---
source:https://en.wikipedia.org/wiki/Selection_sort
---
What is the selection sort algorithm?
<!--question-->
Selection sort is an in-place comparison sorting algorithm.
It has an $O(n^2)$ time complexity, which makes it inefficient on large lists, and generally performs worse than the similar insertion sort.

The algorithm divides the input list into two parts: a sorted sublist of items which is built up from left to right at the front (left) of the list and a sublist of the remaining unsorted items that occupy the rest of the list. Initially, the sorted sublist is empty and the unsorted sublist is the entire input list. The algorithm proceeds by finding the smallest (or largest, depending on sorting order) element in the unsorted sublist, exchanging (swapping) it with the leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries one element to the right.

![Selection sort](images/Selection-Sort-Animation.gif)

Property | Selection Sort
-|-
Data structure | Array
Worst-case performance | $О(n^2)$ comparisons, $О(n)$ swaps
Best-case performance | $О(n^2)$ comparisons, $O(1)$ swaps
Average performance | $О(n^2)$ comparisons, $О(n)$ swaps
Worst-case space complexity | O(1) auxiliary
