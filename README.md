# Heap Sort Algorithm

This repository contains the implementation and analysis of the Heap Sort algorithm in C++.

## **Part (a) Algorithms for Heap Sort**
### 1. Heapify Algorithm
- Maintains the max-heap property.
- Complexity: \(O(\log n)\).

### 2. Build-Heap Algorithm
- Converts an array into a max-heap.
- Complexity: \(O(n)\).

### 3. Heap-Sort Algorithm
- Sorts an array using heap operations.
- Complexity: \(O(n \log n)\).

---

## **Part (b) Analysis**
- **Heapify**: Traverses tree height; \(O(\log n)\).
- **Build-Heap**: Converts array to max-heap; \(O(n)\).
- **Heap-Sort**: Extracts max repeatedly; \(O(n \log n)\).

---

## **Part (c) C++ Implementation**
```cpp
#include <iostream>
#include <vector>
using namespace std;

// Heapify function to maintain the max-heap property
void heapify(vector<int>& arr, int n, int i) {
    int largest = i;           // Initialize largest as root
    int left = 2 * i + 1;      // Left child index
    int right = 2 * i + 2;     // Right child index

    // If left child is larger than root
    if (left < n && arr[left] > arr[largest])
        largest = left;

    // If right child is larger than largest so far
    if (right < n && arr[right] > arr[largest])
        largest = right;

    // If largest is not root
    if (largest != i) {
        swap(arr[i], arr[largest]); // Swap root with largest
        heapify(arr, n, largest);  // Recursively heapify the affected sub-tree
    }
}

// Build-Heap function to convert array into a max-heap
void buildHeap(vector<int>& arr, int n) {
    // Start from the last non-leaf node and move upwards
    for (int i = n / 2 - 1; i >= 0; i--) {
        heapify(arr, n, i);
    }
}

// Heap Sort function
void heapSort(vector<int>& arr) {
    int n = arr.size();

    // Step 1: Build a max-heap
    buildHeap(arr, n);

    // Step 2: Extract elements from the heap one by one
    for (int i = n - 1; i > 0; i--) {
        swap(arr[0], arr[i]);  // Move current root to end
        heapify(arr, i, 0);    // Call heapify on the reduced heap
    }
}

// Function to print the array
void printArray(const vector<int>& arr) {
    for (int num : arr)
        cout << num << " ";
    cout << endl;
}

int main() {
    vector<int> arr = {12, 11, 13, 5, 6, 7};

    cout << "Original Array: ";
    printArray(arr);

    heapSort(arr);

    cout << "Sorted Array: ";
    printArray(arr);

    return 0;
}

