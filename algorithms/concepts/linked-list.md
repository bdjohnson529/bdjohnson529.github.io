---
title: "Linked Lists"
layout: default
topic: algorithm-concepts
order: 1
parent: Algorithms
parent_path: /algorithms/
---
What is the time complexity of adding an element to a dynamic array? A dynamic array allocates space based on the number of elements in the array. Each time the array reaches capacity, the array contents are copied to a new array with twice as many elements.

After adding `X` elements to the array, the array will have made copies of itself a certain number of times. If you add up the copies which are made during each resizing, you would get the following sum
```
1 + 2 + 4 + 8 + 16 ... X
```
The sum can be rewritten
```
X + X/2 + X/4 + X/8 + ... + 1
```
This sum converges to `2X`. Adding `X` elements to the array would take roughly `2X` time. We are usually only concerned with the order of the polynomial, and this algorithm has a time complexity of `O(X)`.