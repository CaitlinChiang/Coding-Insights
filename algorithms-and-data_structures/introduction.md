# Introduction

## Defining an Algorithm
- A set of steps or instructions for completing a task.
- Algorithmic Thinking
  - When a problem is presented, you should be able to break it down into specific steps, then identify the appropriate algorithm to be applied.
  - Always clarify the values that count as inputs.

Guidelines:
  1. Clearly defined problem statement, input, and output.
  2. Must contain a specific set of instructions in a particular order.
  3. Each step in the algorithm must be explicitly clear & distinct.
  4. Should produce a result that is consistent when repeated.
  5. Should actually complete in a finite amount of time.

- Correctness: For any possible input, the algorithm should always terminate. This is proven by mathematical induction.
- Efficiency
  - Time Complexity: The less time the algorithm takes to complete, the more efficient it is.
  - Space Complexity: Good algorithms don't take up too much memory
   

## Evaluating Linear Search
- Start at the beginning of the list, and repeatedly go through all succeeding values until the target value matches.
- For Example:
  - For a target value of n = 100, the algorithm must go through and evaluate 100 values to match it.


## Evaluating Binary Search
- With every value evaluated against the target value, we are able to eliminate half of the values in the range by answering 'is it more than or less than'.
- The values must be sorted.

For Example:
  1. For a target value of n = 100, the algorithm evaluates 50
  2. Eliminates values 1-50
  3. Evaluates 75
  4. Eliminates values 51-75
  5. Evaluates 85
  6. ... Then this pattern repeats until 100 is reached
