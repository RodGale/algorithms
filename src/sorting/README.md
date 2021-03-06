# Sorting Algorithms

## Selection Sort 

- sorts by finding a min to the right of current position and swap with current element.

### Time Complexity

* N^2 /2 compares and N swaps.
* Quadratic time irrespective of input.

## Insertion Sort 
- starting from current element every consecutive element to it's left is compared. If any is less than previous one, they are swapped. If not, move the current element pointer to right and continue.

### Time Complexity
* Worst case: ~N^2/2 compares and swaps if array is sorted in reverse order. Otherwise, its less than quadratic time.
* Best case: Already sorted takes N-1 compares and 0 swaps. 

Better in best and random cases when compared to Selection sort, but not in worst case. Better suited for partially sorted input.

## Shell Sort

- It's idea is to move elements more than one position using an incremental sequence like powers of 2 minus 1, 3x+1, etc. Element at position i is compared with element at i+h, where is 7 in case of 7-sort and swapped if out of order. 
- 1-sort is like a insertion sort. Instead of comparing with element left of it, we compare with elements at distance in multiples of h left of element i.

![Shell Sort example](https://github.com/apoorvam/algorithms/blob/master/assets/shell_sort_example.png?raw=true)

### Time Complexity
* Worst case: N^(3/2). But very fast for smaller input size and less code footprint. Average case complexity cannot be easily defined(linearithmetic).

## Merge Sort
* Uses divide and conquer method to sort.
* Divide array into two halves, recursively sort them, merge two halves.

### Time Complexity
* Time: Uses utmost N log N compares and 6N log N array access to sort any array.
* Space: Uses extra space proportional to N, for auxillary array.

#### Optmizations
* Optimization 1: Use insertion sort for array sizes ~ 7
* Optimization 2: Avoid if already sorted. If biggest element of left subarray is less than smallest element of right subarray,
there is no need of merge.

![Merge sort vizualization](https://github.com/apoorvam/algorithms/blob/master/assets/mergesort_viz.jpeg?raw=true)

## Quick Sort
Idea: 
- Shuffle array(required for performance gains)
- Partition it such that for some index k, arr[k] is in place, all entries to left of k are smaller than arr[k] and
all entries to the right of k are greater than arr[k]
- Sort each piece recursively

It does more compares than merge sort, but this is faster because of less data movement.
Quick sort is in-place, but not stable sorting algorithm.

### Time Complexity

* Best case: N lg N compares
* Worst case: N^2/2 compares (quadratic)
* Average case: ~1.39 N lg N

## 3-way Partitioning

Quick sort takes quadratic time to sort items with duplicates. 3-way partition can perform better than that. Idea is to partition array into 3 parts such that:
* Entries between lt and gt are all equal to partition item
* Entries to left of lt are less than partition item
* Entries to right of gt are greater than partition item

If a[lo] is partition item v,

* a[i] < v, swap v and a[i], increment i and lt
* a[i] > v, swap a[i] and a[gt], decrement gt
* a[i] == v, increment i

### Efficiency

It is entropy optimal. Linear in many cases.
    