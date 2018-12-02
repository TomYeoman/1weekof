# Map

## Summary

A collection (`set`) of keys which have corresponding values to them. Some languages use the term `map` ( E.G javascript / C++ ), whilst others use the erm `dictionary` ( Such as C# ).

* Do not have methods
* May provide methods to retrieve all keys
* They have NO concept of order
* Values can be duplicated, they are not a set

A map can perform a lookup in `O(1)` time although that can degrade to `O(N)` depending on the input

## Usage

Maps are key-value sets, We use them a lot in javascript already

## Example

ES6 provides us a way to create `map` our the box

```javascript
  const myMap = new Map();

  // Keys for the Map can be of any type
  const keyString = 'a string';
  const keyObj = {};
  const keyFunc = function () { };

  // setting the values
  myMap.set(keyString, "value associated with 'a string'");
  myMap.set(keyObj, 'value associated with keyObj');
  myMap.set(keyFunc, 'value associated with keyFunc');

  // 3
  console.log(myMap.size)

  for (var [key, value] of myMap) {
    // 1 ) ​​​​​a string = value associated with 'a string'​​​​​
    // 2) ​​​​​[object Object] = value associated with keyObj​​​​​
    //​​​​​ 3) function () {​​​​​ $_$wf(1); } = value associated with keyFunc​​​​​
    console.log(key + ' = ' + value);
  }
```

