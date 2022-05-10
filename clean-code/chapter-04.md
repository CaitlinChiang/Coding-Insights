# Chapter 04: Comments

- The proper use of comments is to compensate for our failure to express ourself in code. If we were expressive enough, then we would not need comments very much. We probably would not need it at all.
- Sometimes it is just helpful to translate the meaning of some obscure argument or return value into something that’s readable.

For Example: 
```
assertTrue(a.compareTo(a) == 0); // a == a
assertTrue(a.compareTo(b) != 0); // a != b
```

- Used for warnings on specific lines of code.
- Used for TODOs that cannot be done at the moment.
- Amplifies the importance of something that may otherwise seem inconsequential.
- Should not be misleading or filler 'noise'.
- Do not get into the habit of commenting out code because you don't know what to do with it.
- If writing comments, then ensure it describes the code it appears near.
