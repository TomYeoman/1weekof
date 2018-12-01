```javascript
var insertionSort = nums => {
  for (let i = 1; i < nums.length; i++) {
    console.log(nums.length)
    for (let j = 0; j < i; j++) {
      // snapshot(nums);
      if (nums[i] < nums[j]) {
        let spliced = nums.splice(i, 1);
        nums.splice(j, 0, spliced[0]);
      }
    }
  }

  return nums;
};

console.log(insertionSort([4,2,1,4,3]))
```