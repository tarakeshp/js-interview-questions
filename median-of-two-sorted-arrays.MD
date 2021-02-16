# Median of Two Sorted Arrays
### https://leetcode.com/problems/median-of-two-sorted-arrays/

### Solution
```

var findMedianSortedArrays = function (nums1, nums2) {
  const merged_arr = [...nums1, ...nums2].sort((a, b) => a - b);
  const length = merged_arr.length;
  let median_index = 0;
  if (length % 2 == 0) {
    // if length is a even number then median and median -1 and do further median on array values
    const m1 = merged_arr[length / 2 - 1];
    const m2 = merged_arr[length / 2];
    return (m1 + m2) / 2;
  } else {
    median_index = length / 2;
    const r1 = merged_arr[Math.floor(median_index)];
    if (r1 >= 0) return r1;
    const r2 = getR2Value(merged_arr, median_index);
    return r2;
  }
};

function getR2Value(merged_arr, median_index) {
  let cnt = Math.floor(median_index);
  let arr = merged_arr.slice(0, cnt + 1);
  return Math.max(...arr);
}
```

#### Test Data
console.log(findMedianSortedArrays([1], [2, 3, 4, 5, 6, 7, 8, 9, 10])); //5.5
console.log(findMedianSortedArrays([], [-3, -2, -1, 1, 5])); //-1
console.log(findMedianSortedArrays([3], [-2, -1])); //-1.000
console.log(findMedianSortedArrays([1, 3], [2])); //2
console.log(findMedianSortedArrays([1, 2], [3, 4])); //2.5
console.log(findMedianSortedArrays([0, 0], [0, 0])); //2
