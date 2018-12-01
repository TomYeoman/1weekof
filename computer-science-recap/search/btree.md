# Binary search

### Scenario

#1  - We have a name that begins with `K`

#2 - We're searching for a word in a dictionary that begins with `O`

### Solution

The naive solution may be to iterate through the entire database, looking for items which begin with `K` or `O`, however wouldn't it be much easier if instead we start searching from the middle?

This is a search problem - all of these can use the same solution to solve it - using a binary search.

The input to a binary search must always be a sorted list of elements.

### How does it work?

The aim is to guess the best solution given input `O` or `K` with the fewest amount of tries. Binary search provides us a method which when called will tell us whether our guess is too low, too high, or correct.

Given 100 numbers this allows us to always guess the correct answer within 7 steps!

ANother example is given a dictionary of 240,000 words, A binary search can ensure a match is found within just 18 steps!

We can express this as - for any list `n` the search will take `log2n` steps to run int he worst case, whereas a naive search would always take `n` steps.

```javascript
const binary_tree_search = ({ values, searhTerm }) => {
  let low = 0;
  let high = values.length - 1;

  while (low <= high) {

    const mid = Math.ceil(low + (high - low) / 2);
    const midValue = values[mid];

    console.log(midValue)
    console.log(mid)
    console.log(low)
    console.log(high)

    // Match!
    if (midValue === searhTerm) {
      return mid;
    }
    // Value must be in RIGHT half
    else if (midValue < searhTerm) {
      low = mid + 1;
    }
    // Value must be in LEFT half
    else if (midValue > searhTerm) {
      high = mid - 1;
    }
  }

  return `No match found :(`;
}

console.log(binary_tree_search({
  values: [...Array(700)].map((_, i) => i),
  searhTerm: -100
}))
```
