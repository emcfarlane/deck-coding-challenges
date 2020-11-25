source:https://en.wikipedia.org/wiki/Quicksort
---
What is Quicksort?
<!--question-->
Quicksort (sometimes called partition-exchange sort) is an efficient sorting algorithm. Developed by British computer scientist Tony Hoare in 1959 and published in 1961, it is still a commonly used algorithm for sorting. When implemented well, it can be about two or three times faster than its main competitors, merge sort and heapsort.

Quicksort is a divide and conquer algorithm. It first divides the input array into two smaller sub-arrays: the low elements and the high elements. It then recursively sorts the sub-arrays. The steps for in-place Quicksort are:

1. Pick an element, called a pivot, from the array.
2. Partitioning: reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it (equal values can go either way). After this partitioning, the pivot is in its final position. This is called the partition operation.
3. Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.

The base case of the recursion is arrays of size zero or one, which are in order by definition, so they never need to be sorted.

The pivot selection and partitioning steps can be done in several different ways; the choice of specific implementation schemes greatly affects the algorithm's performance.

![Quicksort](images/Sorting_quicksort_anim.gif)

Property | Quicksort
-|-
Worst-case performance | $О(n \log{} n)$
Best-case performance | $О(n \log{} n)$ distinct keys, $O(n)$ equal keys
Average performance | $О(n \log{} n)$
Worst-case space complexity | $О(n)$ total, $O(1)$ auxiliary

### Python Example
```
def quick_sort(data):
    if len(data) < 2:
        return data
    equal = []
    left = []
    right = []
    pivot_index = len(data) // 2
    pivot_value = data[pivot_index]
    # Build the left and right partitions
    for item in data:
        if item == pivot_value:
            equal.append(item)
        elif item < pivot_value:
            left.append(item)
        else:
            right.append(item)
    # Recursively apply quick_sort
    left_ = quick_sort(left)
    right_ = quick_sort(right)
    return left_ + equal + right_
```
