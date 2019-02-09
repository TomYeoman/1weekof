# Set

## Summary

* No sense of order
  * Some implementation will give it in the order it's added, Others the order it's saved in
* Not a list
* No duplication
  * Should error / de-duplicate on add

## Usage

Useful for checking usernames when adding new ones, E.G we can check `does my set already have this username`

## Example

```javascript
const createSet = ({
  array1,
  array2
}) => {
  return new Set(array1, array2);
}

// ​​​​​Set { 1, 2, 3, 4, 5, 6 }​​​​​
console.log(createSet({
  array1 : [1,2,3],
  array1 : [1,2,3,4,5,6],
}))

```

We can also use weakMaps / weakSets which will allow the GC to clean them up ( Useful when holding on to DOM nodes which no longer exist )

