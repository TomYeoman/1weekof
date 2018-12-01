# Big O
In it's most simply terms the bigO's role is to determine the time a function will take to run given X inputs. It tells us this in both terms of time + space

It does this by focusing only on the broad strokes which will largest impact the run-time / space requirements

> Example #1

I.E Given the function `3x² + x + 1`

`3` ( The coeficccient ) : is ignored as this doesn't add much time

`x²` :  This is where bigO takes notice.

> Solution #1

We could express the above function as `O(n²)` where O is absorbing all the fluff

## Logarithm

`log10 100` is like asking *"How many 10's do we multiply to get 100?"* the answer in this case is `2`

Similarly `log2 16` is how many 2's do we need to multiply to get 16? The answer being `4`

In terms of bigO log always equals log2. So in order to determine how many iterations a btree search would require for 100 items, We simply do log2 100 - Which equals 7 ( 2^7 )


# Examples

### O(n)
```javascript
function calculateTotal(values = [1, 2, 3, 4, 5]) {
  return values.reduce((acc, num) => {
    return acc + num;
  })
}
```
We go through all items in values once, so the big O is `O(n)`

### O(n²)
```javascript
function create2DArray(arr1 = [1, 2, 3, 4, 5], arr2 = [4,5,6,7,8]) {
  return values.reduce((acc, num) => {
    return acc + num;
  })
}
```

