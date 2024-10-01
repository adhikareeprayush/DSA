# Selection Sort Algorithm

## Description

Selection Sort is a simple comparison-based sorting algorithm. It works by repeatedly finding the minimum element from the unsorted part of the array and putting it at the beginning of the sorted part.

### Implementation

```cpp
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int min_index = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min_index]) {
                min_index = j;
            }
        }
        if (min_index != i) {
            swap(arr[i], arr[min_index]);
        }
    }
}
```

## How It Works

1. Start with the first unsorted element.
2. Find the minimum element in the unsorted portion of the array (from index i to n-1).
3. Swap the found minimum element with the first unsorted element.
4. Move to the next unsorted element and repeat steps 2-3 until the entire array is sorted.

## Complexity Analysis

- **Time Complexity:** $ O(n²) $

  - The outer loop runs n-1 times.
  - The inner loop runs n-i-1 times for each iteration of the outer loop.
  - This results in (n-1) + (n-2) + ... + 2 + 1 = n(n-1)/2 comparisons, which is O(n²).

- **Space Complexity:** $ O(1) $
  - Selection Sort is an in-place algorithm, using only a constant amount of extra memory.

## Advantages

1. Simple implementation
2. Performs well on small arrays
3. Minimizes the number of swaps ($ O(n) $ swaps)

## Disadvantages

1. Inefficient for large arrays
2. Always O(n²) time complexity, even if the array is already sorted

## Use Cases

- Sorting small arrays or lists
- When memory write is a costly operation
- As a simple sorting algorithm for educational purposes
