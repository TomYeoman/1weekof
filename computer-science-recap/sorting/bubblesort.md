```javascript
const bubbleSort = ({values}) => {
  let finishedSort = false;
  do {
        let hasSwappedThisRound = false;
        for (let x = 0; x < values.length; x++) {

          // Compare each 2 numbers and see if they need swap
          if (values[x] > values[x + 1]) {
            // Swap values
            let swap = values[x];
            values[x] = values[x + 1];
            values[x + 1] = swap;
            hasSwappedThisRound = true;
          }
        }

        if (!hasSwappedThisRound) {finishedSort = true}

  } while (!finishedSort)
  return values;
}

console.log(bubbleSort({ values : [9, 7, 6, 5]}))
```