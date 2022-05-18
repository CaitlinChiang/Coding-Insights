# Algorithms in Code

## Linear Search
```
// Returns the index position of a target value in the list

def linear_search(list, target):
  for i in range(0, len(list)): //len(list) is in constant runtime
    if list[i] == target: 
      return i
  return None
```


## Binary Search
```
// Returns the index position of a target value in the list

def binary_search(list, target):
  first = 0
  last = len(list) - 1

  while first <= last:
    midpoint = (first + last) // 2

    if list[midpoint] == target:
      return midpoint
    if list[midpoint] < target:
      first = midpoint + 1
    if list[midpoint] > target:
      last = midpoint - 1

  return None 
```


## Recursive Binary Search
- Recursive Function: A functions that calls itself
  - Contains 2 base cases: A stopping condition for when the value is obtained and for when the value does not exist
- Recursive Depth: The number of times a recursive function calls itself
- A lot of algorithms involve recursion but for functional programming languages like Python, it prefers an iterative solution which includes loops. It has a maximum recursion depth.

```
def recursive_binary_search(list, target):
  if len(list) == 0: return False

  midpoint = (len(list)) // 2
  if list[midpoint] == target:
    return True
  if list[midpoint] < target:
    return recursive_binary_search(list[midpoint + 1:], target) // Returns a smaller sublist for O(log n)
  if list[midpoint] > target:
    return recursive_binary_search(list[:midpoint], target) // Returns a smaller sublist for O(log n)
```


## Space Complexity
- Measure of how much working or extra storage is needed as a particular algorithm grows.
