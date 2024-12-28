# std::vector<bool> Pitfalls in C++

This repository demonstrates the potential performance issues and unexpected behavior associated with using `std::vector<bool>` in C++.  `std::vector<bool>` is optimized for memory, but this optimization sacrifices performance and standard container behavior. This can lead to significant problems if not carefully considered.

## The Problem

`std::vector<bool>`'s memory optimization involves storing multiple boolean values within a single byte, resulting in a non-standard interface and unpredictable performance.

## How to Reproduce

The `bug.cpp` file contains a simple example illustrating potential performance degradation. The `bugSolution.cpp` demonstrates a more efficient solution using `std::vector<char>` or `std::vector<int>`. 

## Solution

Instead of `std::vector<bool>`, consider using:

* `std::vector<char>`: Each boolean value occupies one byte. 
* `std::vector<int>`:  More space-consuming, but offers better performance for many operations.
* `std::bitset`:  Provides efficient bit-level operations if you're dealing with dense sets of bits.