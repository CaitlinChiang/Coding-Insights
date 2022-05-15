# Chapter 03: Functions

- Have 2 or less arguments ideally, if it needs more then the argument should be an entire class such as 'Address'
  - When passing arguments that hold values beforehand, you may simply set default values incase it is null / empty.

  For Example: 
  ```
  function calculateCustomerPayment(itemsTotalPrice, discount) {
    let discount = discount || 0 // Discount will be set to 0 if null
    return payment * (1 - discount);
  }
  ```

- Indented correctly
- The name should clearly say what they do, in a verb/noun pair.
- Does ONE thing. It should do it well. It should do it ONLY. It focuses on ONE level of abstraction.
  - The Stepdown Rule: Every function is to be followed by those at the next level of abstraction.
  - Either changes the state of an object or returns some information about that object, not both.

For Example: 
```
function emailClients(clients) {
  clients.forEach((client) => {
    const clientRecord = database.lookup(client);
    if (clientRecord.isActive()) {
      email(client);
    }
  });
}
```

Can be improved to:
```
function emailClients(clients) {
  clients.filter(isClientActive).forEach(email);
}

function isClientActive(client) {
  const clientRecord = database.lookup(client);
  return clientRecord.isActive();
}
```

- Don't use flags as function parameters

For Example:
```
function createFile(name, temp) {
  if (temp) {
    fs.create(`./temp/${name}`);
  } else {
    fs.create(name);
  }
}
```

Can be improved to:
```
function createFile(name) {
  fs.create(name);
}

function createTempFile(name) {
  fs.create(`./temp/${name}`)
}
```

- If statements within functions can be broken up into parts too, as the 'else' statement is not always necessary
  - The idea here is that IF the condition is met, then it would return a value / error, otherwise the code will run the next statement

For Example:
```
public String substring(int beginIndex, int endIndex) {
 
  if (beginIndex < 0) {
    throw new StringIndexOutOfBoundsException(beginIndex);
  } else {
    if (endIndex > value.length) {
      throw new StringIndexOutOfBoundsException(endIndex);
    } else {
      int subLen = endIndex - beginIndex;
      if (subLen < 0) {
        throw new StringIndexOutOfBoundsException(subLen);
      }
    }
    return ((beginIndex == 0) && (endIndex == value.length))
        ? this
        : new String(value, beginIndex, subLen);
  }
}
```

Can be improved to:
```
public String substring(int beginIndex, int endIndex) {
  if (beginIndex < 0) {
    throw new StringIndexOutOfBoundsException(beginIndex);
  }
 
  if (endIndex > value.length) {
    throw new StringIndexOutOfBoundsException(endIndex);
  }
 
  int subLen = endIndex - beginIndex;
 
  if (subLen < 0) {
    throw new StringIndexOutOfBoundsException(subLen);
  }
  return ((beginIndex == 0) && (endIndex == value.length))
      ? this
      : new String(value, beginIndex, subLen);
}
```

- Prefer exceptions to returning error codes.

For Example:
```
if (deletePage(page) == E_OK) {
  if (registry.deleteReference(page.name) == E_OK) {
    if (configKeys.deleteKey(page.name.makeKey()) == E_OK) { 
      logger.log("page deleted");
    } else {
      logger.log("configKey not deleted");
    }
  } else {
  logger.log("deleteReference from registry failed"); 
  }
} else {
  logger.log("delete failed");
  return E_ERROR;
}
```

Can be improved to: 
```
private void deletePageAndAllReferences(Page page) throws Exception { 
  deletePage(page);
  registry.deleteReference(page.name); 
  configKeys.deleteKey(page.name.makeKey());
}

private void logError(Exception e) { 
  logger.log(e.getMessage());
}
```

- Use enums for a list of constants, which can be used easier in switch statements within functions.
  - Know when to use switch statements instead of if statements.
  - But when if statements are used, it is best to use them as guard clauses.
```
enum Direction {
  NORTH,
  SOUTH,
  EAST,
  WEST
}
```

- Favor functional programming over imperative programming
```
let totalOutput = 0;

for (let i = 0; i < sampleOutput.length; i++) {
  totalOutput += sampleOutput[i].sampleProperty;
}
```

Can be improved to:
```
const INITIAL_VALUE = 0

const totalOutput = sampleOutput
  .map((e) => e.sampleProperty)
  .reduce((acc, sampleProperty) => acc + sampleProperty, INITIAL_VALUE);
```

- Consider the concept of 'Polymorphism', wherein switch statements are replaced with classes instead. It is a core concept of an object-oriented paradigm that provides a way to perform a single action in different forms.

For Example:
```
class Airplane {
  getCruisingAltitude() {
    switch (this.type) {
      case 'Air Force One':
        return this.getMaxAltitude();
      case 'Cessna':
        return this.getMaxAltitude() - this.getFuelExpenditure();
    }
  }
}
```

Can be improved to:
```
class Airplane {}

class AirForceOne extends Airplane {
  getCruisingAltitude() {
    return this.getMaxAltitude();
  }
}

class Cessna extends Airplane {
  getCruisingAltitude() {
    return this.getMaxAltitude() - this.getFuelExpenditure();
  }
}
```
