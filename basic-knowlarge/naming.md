# Naming

### Arrays

```text
//bad
const fruit = ['apple', 'banana', 'cucumber'];
// okay
const fruitArr = ['apple', 'banana', 'cucumber'];
// good
const fruits = ['apple', 'banana', 'cucumber'];
// great - "names" implies strings
const fruitNames = ['apple', 'banana', 'cucumber'];
```

### Booleans

Booleans can hold only 2 values, `true` or `false`. Given this, using prefixes like “**is**”, “**has**”, and “**can**” will help the reader infer the type of the variable.

```text
// bad
const open = true;
const write = true;
const fruit = true;
```

```text
// good
const isOpen = true;
const canWrite = true;
const hasFruit = true;
```

### Numbers

For numbers, think about words that describe numbers. Words like `maximum`, `minimum`, `total` will .

```text
// bad
const pugs = 3;
```

```text
// good
const minPugs = 1;
const maxPugs = 5;
const totalPugs = 3;
```

### Functions

Functions should be named using a verb, and a noun

```text
// bad
userData(userId)
userDataFunc(userId)
totalOfItems(items)
```

```text
// good
getUser(userId);
calculateTotal(items);
```

functions that return booleans

```text
const checkHasFruit = (user, fruitName) => (
    user.fruits.includes(fruitName)
);
const hasFruit = checkHasFruit(user, 'apple');
```

