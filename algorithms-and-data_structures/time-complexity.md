# Time Complexity

## Efficiency of an Algorithm
- BIG 0: Theoretical definition of the complexity of an algorithm as a function of the size.
  - O(n): Linear Search
  - O(log n) or O(ln n): Binary Search
  - O: Order of magnitude of complexity.
  - Complexity is relative, which means we compare one algorithm against another algorithm in the same problem set, not all algorithms.
  - Evaluate how the algorithm performs in the WORST CASE scenario.


## Constant and Logarithmic Runtime
- O(n): For example, in reading values from 1-100 where the target value is 50, the size of the data set doesn't matter. When we're at step 2 for instance, we're already at that position in the list and all we're doing is reading the value as a singular operation. This will take the same amount of time in any value, therefore our runtime operation is constant, denoted by O(1).
- O(log n): When n is doubled, the number of operations the list takes to reduce to a single element increases by 1.
  - Logarithmic or sub-linear algorithms are preferred to linear because they are more efficient 


## Linear Search & Quadratic Runtime
- Linear search can be advantage in a way to a certain value of n, because the sorting and searching time of binary search adds up.
- When an algorithm works in quadratic time, is it computationally expensive. Small changes in n = significant change in the number of operations carried out. 


## Quasilinear Runtime
- O(n log n): For every value of n, we are going to execute a log n number of operations
- For instance, merge sort has a worst case runtime of O(n log n).
  - It will split the list again and again until the list reaches a singular value. When we're down to a singular value, we can do one sort operation and merge these sub-lists back in the opposite direction.
  - It also carries out comparison operations for sorting.


## Polynomial & Exponential Runtime
- A polynomial runtime is if its worst runtime is in the form of n raised to the k power where k is just some value. These are efficient.
- An exponential runtime is an algorithm with a big o value of some number raised to the nth number.
  - These include brute force algorithms. For example, there are 69 characters. The password is 20 characters long, this means that a singular value in the password can be one out of 69 values. The number of operations an intel cpu with five cores can carry out about 65000 million instructions per second. It will take this intel cpu 2^20 years to brute force the password. 


## Determining Complexity
1. Determine the middle position of the list.
2. Compare the value in the middle to the target element. (constant runtime)
3. Success case and the algorithm ends.
4. If we don't match, the list will be separated into sublists. (logarithmic runtime)
5. The sublists will keep splitting until the value is matched, and the operations it takes to accomplish this is the worst case runtime complexity.
- Not all algorithms hit their worst case, so there is also average run time where it is in between the best and worst case. 
