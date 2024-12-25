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

void heapify(vector<int>& arr, int n, int i) { /*...*/ }
// (Add the full C++ code here)
