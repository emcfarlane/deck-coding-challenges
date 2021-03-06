---
source:https://en.wikipedia.org/wiki/Insertion_sort
---
What is insertion sort?
<!--question-->
Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time.
It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort. However, insertion sort provides several advantages:

- Simple implementation: Jon Bentley shows a three-line C version, and a five-line optimized version.
- Efficient for (quite) small data sets, much like other quadratic sorting algorithms
- More efficient in practice than most other simple quadratic (i.e., O(n2)) algorithms such as selection sort or bubble sort
- Adaptive, i.e., efficient for data sets that are already substantially sorted: the time complexity is O(kn) when each element in the input is no more than k places away from its sorted position
- Stable; i.e., does not change the relative order of elements with equal keys
- In-place; i.e., only requires a constant amount O(1) of additional memory space
- Online; i.e., can sort a list as it receives it

When people manually sort cards in a bridge hand, most use a method that is similar to insertion sort

![Insertion sort](https://upload.wikimedia.org/wikipedia/commons/4/42/Insertion_sort.gif)

Property | Insertion Sort
-|-
Data structure | Array
Worst-case performance | $О(n^2)$ comparisons and swaps
Best-case performance | $О(n)$ comparisons, $O(1)$ swaps
Average performance | $О(n^2)$ comparisons and swaps
Worst-case space complexity | $О(n)$ total, $O(1)$ auxiliary

### Python Example
```
def insertion_sort(data):
  if len(data) < 2:
      return data
  for r in range(1, len(data)):
    for l in range(r):
      if data[r] < data[l]:
        temp = data[r]
        data[l+1:r+1] = data[l:r]
        data[l] = temp
  return data
```
