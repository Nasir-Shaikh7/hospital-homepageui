## Problem Statement

Given an array of integers `nums` and an integer `target`, identify two numbers in the array that sum up to the `target` and return their indices. It is guaranteed that there is only one solution for each input and you cannot use the same element twice.

## Examples:

1. **Input:** nums = [2, 7, 11, 15], target = 9
   **Output:** [0, 1]
   **Explanation:** nums[0] + nums[1] = 2 + 7 = 9, thus return [0, 1].

2. **Input:** nums = [3, 2, 4], target = 6
   **Output:** [1, 2]
   **Explanation:** nums[1] + nums[2] = 2 + 4 = 6, thus return [1, 2].

3. **Input:** nums = [3, 3], target = 6
   **Output:** [0, 1]
   **Explanation:** nums[0] + nums[1] = 3 + 3 = 6, thus return [0, 1].

## Preliminary Knowledge

- Hash Map (Dictionary in Python)

## Potential Companies

- ByteDance
- Baidu
- Tencent
- Adobe
- Airbnb
- Amazon
- Apple
- Bloomberg
- Dropbox
- Facebook
- LinkedIn
- Microsoft
- Uber
- Yahoo
- Yelp

## Approach

A brute-force method would involve using two loops, resulting in a time complexity of O(N^2). A more efficient approach uses a hash map to store numbers and their indices, which allows us to reduce the time complexity significantly.

### Key Points

- Convert the problem of finding two numbers that sum to `target` into finding if `target - currentNumber` exists in the hash map.
- Use a hash map to map each number to its index.
- Trade a bit of space for a significant gain in time efficiency by reducing the search operation from O(N) to O(1).

## Code Implementation

### JavaScript:

```javascript
const twoSum = function(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (map.has(complement)) {
            return [map.get(complement), i];
        }
        map.set(nums[i], i);
    }
};
```

### Python:

```python
class Solution:
    def twoSum(self, nums, target):
        num_map = {}
        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], i]
            num_map[num] = i
```

## Complexity Analysis

- **Time Complexity:** O(N) as we traverse the list containing N elements only once. Each look-up in the table costs O(1) on average.
- **Space Complexity:** O(N) as the extra space required depends on the number of items stored in the hash map, which stores at most N elements.

By using a hash map, we optimize the search process, making the solution very efficient for practical purposes. This technique is crucial for handling similar problems efficiently in competitive programming or software development in industry.git