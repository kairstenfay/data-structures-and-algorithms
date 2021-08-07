# Algorithms
A cheat sheet of common algorithms with notes paraphrased or copied directly from [Wikipedia](https://en.wikipedia.org).
See relevant links under section headers.

- [Algorithms](#algorithms)
  - [Searching algorithms](#searching-algorithms)
    - [Breadth-first search](#breadth-first-search)
  - [Sorting algorithms](#sorting-algorithms)
    - [Bucket sort](#bucket-sort)
    - [Insertion sort](#insertion-sort)
    - [Merge sort](#merge-sort)
    - [Quick sort](#quick-sort)


## Searching algorithms

### Breadth-first search


## Sorting algorithms

### Bucket sort
[See Wikipedia page](https://en.wikipedia.org/wiki/Bucket_sort)

The first step is to initialize buckets and find maximum value in the array, which can be done in O(n) time.
Scattering each element to its bucket also costs O(n) time.
Assuming insertion sort is used to sort each bucket, the next step costs the sum of O(n<sup>2</sup><sub>i</sub>) where n<sub>i</sub> is the length of each bucket, which evaluates to O(n<sup>2</sup>/k + n).
The last step of the bucket sort is concatenating the sorted objects in each buckets, which requires O(k) time.

| Case | Complexity | Comment |
| --- | --- | --- |
| Worst-case performance | O(n<sup>2</sup>) | Occurs when all elements are placed in a single bucket.
| Best-case performance | O(n) | When k ~~ n. See notes above.
| Average performance | O(n + n<sup>2</sup>/k + k) | See notes above.
| Worst-case space complexity | O(n*k) |


### Insertion sort
[See Wikipedia page](https://en.wikipedia.org/wiki/Insertion_sort)

Insertion sort is one of the fastest algorithms for sorting very small arrays, even faster than quicksort.
Good quicksort algorithms use insertion sort for arrays smaller than a certain threshold (commonly around 10).

| Case | Complexity | Comment |
| --- | --- | --- |
| Worst-case performance | O(n<sup>2</sup>) | Input is sorted in reverse order
| Best-case performance | O(n) | Input is already sorted
| Average performance | O(n<sup>2</sup>) |
| Worst-case space complexity | O(n), O(1) auxiliary


### Merge sort
[See Wikipedia page](https://en.wikipedia.org/wiki/Merge_sort)

Merge sort is a comparison-based sorting algorithm.
It is more efficient than quicksort for some types of lists if the data to be sorted can only be accessed sequentially.
Merge sort is a stable sort.
Merge sort's most common implementation does not sort in place, therefore extra memory must be allocated.
In the worst case, merge sort does about 39% fewer comparisons than quicksort does in the average case.
Merge sort's worst case complexity, O(nlogn), is the same as quicksort's best case, and merge sort's best case takes about half as many iterations as the worst case.
Therefore, merge sort may perform better on inputs that are slow to access.

| Case | Complexity | Comment |
| --- | --- | --- |
| Worst-case performance | O(nlogn) |
| Best-case performance | O(nlogn) or O(n) | Typical or natural variant
| Average performance | O(nlogn) |
| Worst-case space complexity | O(n) with O(n) or O(1) auxiliary | Achieve constant extra space with linked lists


### Quick sort
[See Wikipedia page](https://en.wikipedia.org/wiki/Quicksort)

Merge sort is a divide-and-conquer, comparison-based sorting algorithm.
It sorts in-place.
It is not a stable sort.
When implemented well, quicksort can be about two or three times faster than its main competitors, merge sort and heapsort.
Quicksort has some disadvantages which complicate its efficient parallelization, not only because of the depth of its divide-and-conquer tree which is dependent on the algorithm's choice of pivot, but also because it's difficult to parallelize the partitioning step efficiently in-place.


| Case | Complexity | Comment |
| --- | --- | --- |
| Worst-case performance | O(n<sup>2</sup>) | Rare, but happens when sublists returned by partitioning routine is of size n - 1. May occur if pivot is smallest or largest element in list, or in some implementations (e.g. Lomuto partition scheme), when all elements are equal.
| Best-case performance | O(nlogn) or O(n) | Simple partition or three-way partition and equal keys
| Average performance | O(nlogn) |
| Worst-case space complexity | O(n) auxiliary or O(logn) auxiliary | Naive or Hoare 1962
