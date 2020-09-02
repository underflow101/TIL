# TIL 2020.09.02
---

- Timsort is Python's official sort algorithm (+ Java, and more!)
    - e.g. `list.sort()` uses Timsort
- Timsort grants O(N log N) in worst case scenario, and goes O(N) in the best case
- Timsort is stable and type-safe!
- Basic theory of Timsort is combination hybrid of Merge Sort & Insertion Sort
- It is hard to code:
    - Two or more consecutive elements non-descending or strictly descending are grouped in a unit called `run`, and the information about them is stacked on a stack and sorted by Insertion Sort to the size of `minrun` having a value between 32 and 64. Then the `minrun` is merged and the whole is sorted.
- Timsort is very practical sort algorithm, which has reduced computational cost where data are previously sort-of-sorted.
    - It does not sort where the point of data are already sorted.
- So Timsort works very well with real-world data, unlike Quick Sort.

### <b>[Example Code URL](https://github.com/underflow101/code-example/blob/master/sort/timsort.py)</b>