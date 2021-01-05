---
source:https://en.wikipedia.org/wiki/Merge_sort
---
What is Merge sort?
<!--question-->
Merge sort is an efficient, general-purpose, comparison-based sorting algorithm. Most implementations produce a stable sort, which means that the order of equal elements is the same in the input and output. Merge sort is a divide and conquer algorithm that was invented by John von Neumann in 1945.[2] A detailed description and analysis of bottom-up mergesort appeared in a report by Goldstine and von Neumann as early as 1948.[3]

Conceptually, a merge sort works as follows:

1. Divide the unsorted list into n sublists, each containing one element (a list of one element is considered sorted).
2. Repeatedly merge sublists to produce new sorted sublists until there is only one sublist remaining. This will be the sorted list.

![Merge sort](images/Merge-sort-example-300px.gif)

Property | Merge sort
-|-
Worst-case performance | $О(n \log{} n)$
Best-case performance | $О(n \log{} n)$ typical, $O(n)$ natural variant
Average performance | $О(n \log{} n)$
Worst-case space complexity | $О(n)$ total with $O(n)$ auxiliary, $О(1)$ auxiliary with linked lists

### Python Example
```
def merge_sort(data):
    if len(data) < 2:
        return data
    mid = len(data) // 2
    left = data[:mid]
    right = data[mid:]
    left = merge_sort(left)
    right = merge_sort(right)
    return merge(left, right)

def merge(left, right):
    l = 0
    r = 0
    result = []
    while l < len(left) and r < len(right):
        if left[l] < right[r]:
            result.append(left[l])
            l += 1
        else:
            result.append(right[r])
            r += 1
    # Copy remaining elements
    while l < len(left):
        result.append(left[l])
        l += 1
    while r < len(right):
        result.append(right[r])
        r += 1
    return result
```
