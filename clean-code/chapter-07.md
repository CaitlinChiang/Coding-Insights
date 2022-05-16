# Chapter 07: Error Handling

- Error handling is wrong if it obscures logic, and projects shouldn't be dominated by them.
- Use exceptions rather than return codes.
- Try blocks are like transactions, and the catch statement has to leave the program in a consistent state no matter what happens in the try block.
- Exceptions thrown should provide enough context to determine the source and location of an error.
  - Include what operation failed, its source, and the type of failure (ex. device failures, network failures, etc.).
- Avoid returning null, consider throwing an exception or returning a SPECIAL CASE object instead.
- Avoid passing null into methods.
