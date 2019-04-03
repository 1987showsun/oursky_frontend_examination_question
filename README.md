## Question 4

### Please explain what is the bug in the following Javascript function, and how to correct it.

### Example:
> Error
```js
function createArrayOfFunctions(y) {
  var arr = [];
  for(var i = 0; i<y; i++) {
    arr[i] = function(x) { return x + i; }
  }
  return arr;
}
```

### Answer:
+ 1.
```js
function createArrayOfFunctions(y) {
  var arr = [];
  for(var i = 0; i<y; i++) {
    arr[i] = function(x) { return x + i; }(i)
  }
  return arr;
}
```
> or
+ 2.
 ```js
function createArrayOfFunctions(y) {
  var arr  = [];
  var arr2 = [];
  for(var i = 0; i<y; i++) {
    arr[i] = function(x) { return x + i; }
    arr2   = [ ...arr2, arr[i](i) ];
  }
  return arr2;
}
 ```
