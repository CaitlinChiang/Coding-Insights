# Chapter 06: Objects and Data Structures

- The Law of Demeter: A module should not know about the innards of the objects it manipulates. A method F of a class C should only call the methods of these: 
  - C
  - An object created by F
  - An object passed as an argument to F
  - An object held in an instance variable of C
- Objects hide the data abstraction and expose methods that operate the data.
- Data structures expose your data and do not have significant methods.