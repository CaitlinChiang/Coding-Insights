# Chapter 02: Meaningful Names

- Names should reveal intent: Why it exists, what it does, and how it is used.
- Variable names with a singular letter such as 'i' or 'd' unless in a local iteration loop is discouraged.

Example code for a mine sweeper game:
```
public List<int[]> getThem() {
  List<int[]> list1 = new ArrayList<int[]>(); for (int[] x : theList)
    if (x[0] == 4) 
      list1.add(x);
  return list1; 
}
```

Can be improved by simply using meaningful names and creating a class for cells instead of using int[]:
```
public List<Cell> getFlaggedCells() {
  List<Cell> flaggedCells = new ArrayList<Cell>(); 
  for (Cell cell : gameBoard)
    if (cell[STATUS_VALUE] == FLAGGED)
      flaggedCells.add(cell);
  return flaggedCells; 
}
```

- Ensure that the names are meaningful and distinct. A bad example would be ProductInfo and ProductData, where both are similar.
- Variable names should be pronounceable for ease of communication.
- Classes and objects should have noun or noun phrase names (ex. Customer, Account, Address), not verbs.
- Methods should have verb or verb phrase names (ex. deletePage, postPayment).
- Accessors, mutators, and predicates should be named for their value and prefixed with 'get', 'set', and 'is'.

For Example: 
```
string name = employee.getName(); 
customer.setName("mike");
if (paycheck.isPosted())...
```

- Pick one word for one abstract concept. 
  - For instance, only choose one between 'fetch', 'retrieve', and 'get'.
  - You could end up with many classes that have, for example, an add method. It's okay as long as the parameter lists and return values of the various add methods are semantically equivalent. 'add' cannot be used for both adding two values and for adding data into a collection, in this case it will be better to use 'insert' or 'append'. 
- Instead of having multiple variables laying around such as 'street', 'houseNumber', and 'city', these can be part of a bigger concept or class named 'Address'.
