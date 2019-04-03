## Question 3

### Write a function that takes an array of integers as input. For each integer, output the next fibonacci number. Solution that work both cpu and memory efficient are appreciated.

### Example:
* nextFibonacci([1,22,9]) = [2,34,13];

### Answer:
```js
const nextFibonacci = ( arr ) => {
  const _maxNumber = [...arr].sort((a,b)=>Number(a)-Number(b))[arr.length-1];
  let   _FN        = [1,1];
  
  for( let i=0 ; i<_maxNumber ; i++ ){
    if( i>0 ){
      let _sum = _FN[i-1]+_FN[i];
      _FN = [..._FN, _sum];
      if( _sum>_maxNumber ) break;
    }
  }

  return arr.map( item => {
    return _FN.find( findItem => findItem>item)
  })
}
```
