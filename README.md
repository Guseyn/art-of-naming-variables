## The art of naming variables
## Arrays
```javascript
// bad
const fruit = ['apple', 'banana', 'cucumber']

// bad
const fruitArr = ['apple', 'banana', 'cucumber']

// bad
const fruits = ['apple', 'banana', 'cucumber']

// great - "names" implies strings
const fruitNames = ['apple', 'banana', 'cucumber']

// great
const fruits = [{
    name: 'apple',
    genus: 'malus'
}, {
    name: 'banana',
    genus: 'musa'
}, {
    name: 'cucumber',
    genus: 'cucumis'
}]
```

## Booleans
Booleans can hold only 2 values, `true` or `false`. Given this, using prefixes like **“is”**, **“has”**, and **“can”** will help the reader infer the type of the variable. But it also specify context of the variable like a noun that the boolean variable is attached to.
```javascript
// bad
const open = true
const write = true
const fruit = true

// bad
const isOpen = true
const canWrite = true
const hasFruit = true
const wasEgg = true
const eatAble = true
const haveCustomFilters = true
const hasCustomFilter = true
const areCustomFiltersApplied = true
const isCustomFilterApplied = true

// good
const itIsOpen = true
const itCanWrite = true
const itHasFruit = true
const itWasEgg = true
const itIsEatAble = true
const itHasCustomFilters = true
const itHasCustomFilter = true
const thereAreCustomFiltersApplied = true
const itIsCustomFilterApplied = true
```

`it` can be replaced for the context with concrete noun.

And then you can use with `if` statement, and it would look natural in English:

```js
if (doorIsOpen) {
  // close it
}
```

## Functions
What about predicate functions (functions that return booleans)?
```javascript
const checkWhetherItHasFruit = (user, fruitName) => (
    user.fruits.includes(fruitName)
);
const itHasFruit = checkWhetherItHasFruit(user, 'apple')
```

Functions should be named using a `verb` if they return void, and a `noun` if they return something. When functions perform some type of action on a resource, its name should reflect that. A good format to follow is `actionResource`. For example, getUser.
```javascript
// bad
getUser(db)
getUser(xml)

// good
const userRetrievedFromDB = userFromDB()
const userParsedFromXML = userFromXML()
```
