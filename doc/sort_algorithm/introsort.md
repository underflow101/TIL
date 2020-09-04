# TIL 2020.09.04
---

- Introsort is an official sort algorithm of C++
    - Actually it is a bit different from real introsort:
        - in C++'s std::sort(), it uses Introsort at first, and then uses Insertion Sort later
- Introsort is a combination of Quick Sort & Heap Sort
- Introsort grants O(N log N) in worst case scenario (>= C++11)
    - before it was C++03, possible worst case scenario was O(N^2)
- C++'s introsort is 20% ~ 50% faster than hand-coded Quicksort, and 250% ~ 1,000% faster than C qsort library function
    - Reference: [ref URL](https://www.geeksforgeeks.org/c-qsort-vs-c-sort/)
    - In C++'s introsort, it uses inlining with `std::less::operator()` by default for computational speed
- Introsort is basically almost the same logic with Quicksort, but has a variable called `maxdepth` to limit recursive call, in case data are biased. (which is almost the case in real life.)
- Introsort in C++ is also type-safe

### Introsort Pseudocode
<pre><code>procedure sort(A : array):
    let maxdepth = ⌊log(length(A))⌋ × 2
    introsort(A, maxdepth)

procedure introsort(A, maxdepth):
    n ← length(A)
    p ← partition(A)  // assume this function does pivot selection, p is the final position of the pivot
    if n ≤ 1:
        return  // base case
    else if maxdepth = 0:
        heapsort(A)
    else:
        introsort(A[0:p], maxdepth - 1)
        introsort(A[p+1:n], maxdepth - 1)</code></pre>

### [Introsort Example Code](https://gist.github.com/praserocking/5280579)