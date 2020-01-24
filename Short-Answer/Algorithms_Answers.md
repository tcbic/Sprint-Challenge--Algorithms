#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

```python
a)  a = 0                    # O(1)               
    while (a < n * n * n):   # While loop: O(n)
      a = a + n * n          
```
# Time complexity: O(1) + O(n) = O(n)

```python
b)  sum = 0                  # O(1)
    for i in range(n):       # For loop: O(n)
      j = 1
      while j < n:           # While loop: O(log n)
        j *= 2
        sum += 1
```

# Time complexity: O(1) + (O(n) * O(log n)) = O(n log n)

```python
c)  def bunnyEars(bunnies):             
      if bunnies == 0:                  # O(1)
        return 0

      return 2 + bunnyEars(bunnies-1)   # O(n + 1)
```

# Time complexity: O(1) + O(n + 1) = O(n)

## Exercise II

Algorithm:
inputs- n (number of stories), k (number of eggs)
output- f (the lowest floor at which an eggs breaks)

In thinking about this problem, using binary search seems like an appropriate solution to help optimize finding f.

What would this look like?

Given n, find the halfway point by creating a list of length n and dividing it by two. The resulting number is equal to what I'll define as half. Use half to now create two separate lists (part_a = [: half] and part_b = [half :]). Drop an egg from the floor defined by half. 

If we drop the egg and it breaks, we know that we can limit our search to part_a. 
If we drop the egg and it doesn't break, we know that we can limit our search
to part_b. 

We would continue this methodology as a way of process of elimination to find the lowest floor at which the egg breaks.

Time complexity of binary search: O(log n)