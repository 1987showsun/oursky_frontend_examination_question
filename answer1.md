## Question 1

### Write a function that takes two arrays as input, each array contains a list of A-Z; Your program should return True if the 2nd array is a subset of 1st array, or False if not.

### For example:
-- isSubset([A,B,C,D,E], [A,E,D]) = true
-- isSubset([A,B,C,D,E], [A,D,Z]) = false
-- isSubset([A,D,E], [A,A,D,E])   = true

```js
const isSubset = (a,b) => {
  return b.find( findItem_B => {
    return !a.includes(findItem_B);
  })!=undefined ? false : true;
}
```
