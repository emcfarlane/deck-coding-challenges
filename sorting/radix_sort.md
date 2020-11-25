source:https://en.wikipedia.org/wiki/Radix_sort
--- 
What is Radix sort?
<!--question-->
Radix sort is a non-comparative sorting algorithm. It avoids comparison by creating and distributing elements into buckets according to their radix. For elements with more than one significant digit, this bucketing process is repeated for each digit, while preserving the ordering of the prior step, until all digits have been considered. For this reason, radix sort has also been called bucket sort and digital sort.

Radix sorts can be implemented to start at either the most significant digit (MSD) or least significant digit (LSD). For example, with 1234, one could start with 1 (MSD) or 4 (LSD).

### Example Least Significant Digit
Input list (base 10): 
`[170, 45, 75, 90, 2, 802, 2, 66]`

1. Starting from the rightmost (last) digit, sort the numbers based on that digit: 
`[{170, 90}, {02, 802, 02}, {45, 75}, {66}]`
Notice that a 0 is prepended for the two 2s so that 802 maintains its relative order as in the previous list (i.e. placed before the second 2) based on the merit of the second digit.

2. Sorting by the next left digit:`[{02, 802, 02}, {45}, {66}, {170, 75}, {90}]`

3. And finally by the leftmost digit:
`[{002, 002, 045, 066, 075, 090}, {170}, {802}]`

Each step requires just a single pass over the data, since each item can be placed in its bucket without comparison with any other element.

Property | Radix sort
-|-
Worst-case performance | $О(w \cdot n)$ where w is the number of bits required to store each key.
Worst-case space complexity | $О(w + n)$

### Python Example
```
def radix_sort(array, base=10):
    if not array:
        return []
    max_element = max(array)
    max_digits = len(str(abs(max_element)))
    curr_array = array
    for digit in range(max_digits):
        buckets = [[] for _ in range(base)]
        for item in curr_array:
            buckets[(item//(base**digit))%base].append(item)
        curr_array = []
        for bucket in buckets:
            curr_array.extend(bucket)
    return curr_array
```
