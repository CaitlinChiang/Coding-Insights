# Chapter 13: Concurrency

- Concurrency is a decoupling strategy: decouples what gets done from when it gets done
- Consider a scenario where a large data set needs to be processed for a solution to be implemented, then perhaps each data set could be processed on a different computer, such that multiple data sets are being processed simultaneously.
- Ideas regarding concurrency:
  1. Does not always improve performance.
  2. Design changes when writing concurrent programs.
      - Design of a concurrent algorithm is different from the design of a single-threaded system.
  3. Understanding concurrency issues are important for working with containers (ex. Web, EJB containers)
  4. Incurs some overhead in performance and additional code.
  5. Complex, even for simple problems.
  6. Bugs aren't repeatable.
  7. Requires a fundamental change in design strategy.
      - Concurrency-related code has its own life cycle of development, change, and tuning.
  8. Each class should have a unique responsibility.
  