---
author: Edson Ayllon
category: algorithm
tags: 
- mathematics
- sequence
twitter: https://twitter.com/relativeread
---

## Algo 1-2019

# Fibonaacci Algorithm

## 1. Scope

Does Fibonacci using a recursive function. 

## 2. Significance & Use

Fibonacci numbers are used in several other algorithms, including, but not limited to:
- Scrum Poker: gamified effort estimates for development goals in software development
- Psuedorandom Number Generation
- Computational run-time analysis of Euclid's algorithm
- Fibonacci coding
- Polyphase version of the merge sort algorithm 
- Fibonacci retracement in technical analysis

## 3. Algorithm & Code

Fibonacci adds a new item by taking the sum of the previous 2 items [1]. 

![fibonacci](https://latex.codecogs.com/gif.latex?F_n%20%3D%20F_%7Bn-1%7D%20&plus;%20F_%7Bn-2%7D)

This function takes in a seed in a 2 value list, and number specifying the number of items returned in the sequence.

```python
# example

seed = [1, 1]
size = 10

sequence = fibonacci(seed, size)
> [1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
```

If a sequence size of 2 or less is specified, the seed list is returned as is.

This sequence is done with a recursive algorithm. If the size hasn't reached the max, the size increments towards the max and the previous two numbers added and appended to the sequence, calling itself with the new sequence and new max progress until the maximum sequence length specified is reached.

```python
def fibonacci(_sequence, _size):
    if _size - 2 > 0:
        _size -= 1
        _sequence.append(sum(_sequence[-2:]))
        fibonacci(_sequence, _size)
    return _sequence
```

## References

[1] http://mathworld.wolfram.com/FibonacciNumber.html
