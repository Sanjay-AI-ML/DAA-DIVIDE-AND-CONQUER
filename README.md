# DAA - Divide and Conquer (C Implementations)

This repository contains C implementations of classic **Divide and Conquer** and algorithmic problems commonly studied in **Design and Analysis of Algorithms (DAA)**.

## 📌 Problem Overview

| # | File Name | Problem Name | Approach / Strategy | Time Complexity | Space Complexity |
|---|---|---|---|---|---|
| 1 | `1-Number of Zeros in a Given Array` | Count Zeros in Binary Array | Modified Binary Search (First Zero Occurrence) | $\mathcal{O}(\log N)$ | $\mathcal{O}(\log N)$ recursive |
| 2 | `2-Majority Element` | Majority Element Detection | Boyer-Moore Voting Algorithm | $\mathcal{O}(N)$ | $\mathcal{O}(1)$ |
| 3 | `3-Finding Floor Value` | Finding Floor Value in Sorted Array | Binary Search (Lower Bound Floor) | $\mathcal{O}(\log N)$ | $\mathcal{O}(1)$ |
| 4 | `4-Two Elements sum to x` | Two Elements Sum to X | Two-Pointer Recursive Search | $\mathcal{O}(N)$ | $\mathcal{O}(N)$ recursive |
| 5 | `5-Implementation of Quick Sort` | Quick Sort Algorithm | Divide & Conquer (Lomuto Partition) | $\mathcal{O}(N \log N)$ avg | $\mathcal{O}(\log N)$ stack |

---

## 📖 Problem Details

### 1. Count Zeros in Binary Array (`1-Number of Zeros in a Given Array`)
- **Objective:** Given a sorted array consisting of 1s followed by 0s, determine the total number of zeros efficiently.
- **Approach:** Binary search to locate the index of the first zero:
  - If `arr[mid] == 0` and either `mid == 0` or `arr[mid - 1] == 1`, `mid` is the transition point.
  - Recurse left if mid is zero, otherwise recurse right.
  - Total zeros = `n - index`.

### 2. Majority Element (`2-Majority Element`)
- **Objective:** Identify the element that appears more than $\lfloor n/2 \rfloor$ times in an array.
- **Approach:** Boyer-Moore Voting Algorithm:
  - Maintain a candidate and a counter. Increment when the current element matches candidate, decrement otherwise.
  - When count reaches 0, select the current element as the new candidate.

### 3. Finding Floor Value (`3-Finding Floor Value`)
- **Objective:** Given a sorted array and an integer $x$, find the floor value (the greatest element in the array smaller than or equal to $x$).
- **Approach:** Iterative binary search:
  - If `a[mid] <= x`, save `a[mid]` as candidate floor and search right (`low = mid + 1`).
  - If `a[mid] > x`, search left (`high = mid - 1`).

### 4. Two Elements Sum to X (`4-Two Elements sum to x`)
- **Objective:** Find two elements in a sorted array that sum to a target value $x$.
- **Approach:** Two-pointer recursive search initialized at `low = 0` and `high = n - 1`:
  - If `arr[low] + arr[high] == x`, print pair and terminate.
  - If sum is less than $x$, increment `low`.
  - If sum is greater than $x$, decrement `high`.

### 5. Quick Sort (`5-Implementation of Quick Sort`)
- **Objective:** Sort an array of $n$ integers using the divide-and-conquer paradigm.
- **Approach:** Lomuto partitioning:
  - Choose `arr[high]` as pivot.
  - Reorder array so elements less than or equal to pivot precede elements greater than pivot.
  - Recursively apply quick sort on left and right sub-arrays.

---

## 🚀 How to Run

Compile and run any solution using GCC:

```bash
# Example: Compile Quick Sort
gcc "5-Implementation of Quick Sort" -o quicksort

# Run executable
./quicksort
```

---

## 👤 Author
- **Sanjay R** ([@Sanjay-AI-ML](https://github.com/Sanjay-AI-ML))
