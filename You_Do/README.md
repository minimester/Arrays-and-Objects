# Array Prompts

<details><summary>Even Numbers Prompt</summary>


You are given an integer array with `numbers`, i.e. `[1,2,3,4,5,6,7]`.

Given a number in the array, write a function called `isEven` which console logs a number if that number is even, i.e. when the number is divided by 2, it has no remainder.

### Examples

| Input | Output (Prints Out) | Explanation |
| -------- | ----- |  ----- | 
| `isEven([1,2,3])` | `2` | Looping through the array, the only item that gets printed out is `2`, because `2/2=1` and has no remainder.|
| `isEven([4,3,2,1])` | `4, 2` | Looping through the array, the only items that get printed out are `4` and `2`, because `4/2=2` and `2/2=1` and both of them have no remainder.|
| `isEven([9])` | ` ` | Looping through the array, no item gets printed out, because `9/2` has a remainder of 1. |

_______
</details>

<details><summary>Add One Prompt</summary>


You are given a large integer represented as an integer array `digits`, where each `digits[i]` is the i-th digit of the integer. In other words, if you're given a large integer `1005`, then your `digits` array will be `[1,0,0,5]`. 

Given a large integer, write a function called `addOne` which increments the large integer by one and returns the result in an array of `digits`.

### Examples

| Input | Output (Prints Out) | Explanation |
| -------- | ----- |  ----- | 
| `addOne([1,2,3])` | `[1,2,4]` | The array represents the integer 123. Incrementing by one gives 123 + 1 = 124. Thus, the result should be [1,2,4].|
| `addOne([4,3,2,1])` | `[4,3,2,2]` | The array represents the integer 4321. Incrementing by one gives 4321 + 1 = 4322. Thus, the result should be [4,3,2,2].|
| `addOne([9])` | `[1,0]` | The array represents the integer 9. Incrementing by one gives 9 + 1 = 10. Thus, the result should be [1,0]. |

_______
</details>

<details><summary>Two Number Sum Prompt (Challenge)</summary>

Given an array of integers called `nums` and an integer variable called `target`, write a function called `twoSum` which returns the indices of the two numbers in the `nums` array, such that they add up to `target`. Return -1 if no two numbers in the array sum up to the `target`. 

You may assume that each input would have exactly one solution, and you may not use the same element twice.

### Examples

| Input | Output (Prints Out) | Explanation |
| -------- | ----- |  ----- | 
| `twoSum(nums = [2,7,11,15], target = 9)` | `[0,1]` | The `num[0] = 2` and `num[1] = 7` which sum up to the target `9`, so we return the indices `[0,1]`. `num[0] + num[1] = 9`|
| `twoSum(nums = [3,2,4], target = 6)` | `[1,2]` | The `num[1] = 2` and `num[2] = 4` which sum up to the target `6`, so we return the indices `[1,2]`. `num[1] + num[2] = 6`|
| `twoSum(nums = [3,3], target = 6)` | `[0,1]` | The `num[0] = 3` and `num[1] = 3` which sum up to the target `6`, so we return the indices `[0,1]`. `num[0] + num[1] = 6`|
| `twoSum(nums = [310,15,43,23], target = -10)` | `-1` | There's no 2 numbers in the array that sum upto -10. |


</details>


# Objects Prompts

<details><summary>Majority Element Prompt</summary>

Given an array nums of size `n`, write a function called `findMajorityElement` which returns the majority element from the array. If no majority element can be found, return `-1`.

Note that the majority element is the element that appears more than `⌊n / 2⌋` times in the array, where `n` is the size of the array.

Hint: It would be best to use an object, as you implement your function. 

### Examples

| Input | Output (Prints Out) | Explanation |
| -------- | ----- |  ----- | 
|`findMajorityElement([3,2,3])`| 3 | The element 3 appears 2 times in the array which is greater than `⌊3 / 2⌋`|
| `findMajorityElement([2,2,1,1,1,2,2])` | 2 | The element 2 appears 4 times in the array which is greater than `⌊7 / 2⌋` |
| `findMajorityElement([1,2,3])` | -1 | No element appears greater than `⌊3 / 2⌋` times  |

___
</details>

<details><summary>Converting Roman Numerals to Integers Prompt (Challenge)</summary>

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

| Symbol | Value |
| -------- | ----- | 
| I |            1|
|V    |         5|
|X     |        10|
|L      |       50|
|C       |      100|
|D        |     500|
|M         |    1000|

For example, 2 is written as II in roman numeral, just two one's added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. 

There are six instances where subtraction is used:

- I can be placed before V (5) and X (10) to make 4 and 9. 
- X can be placed before L (50) and C (100) to make 40 and 90. 
- C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numberal, write a function called `numberConversion` which converts a roman numeral to an integer. Make sure you use an object in your implementation.

Note: The parameters to your `numberConversion` function should be a string and your output should be an integer. 

### Examples

| Input | Output (Prints Out) | Explanation |
| -------- | ----- |  ----- | 
| `numberConversion( 'III' )` | 3 | 3 is represented as 3 ones. |
| `numberConversion( 'LVIII' )` | 58 | L = 50, V = 5, III = 3. |
| `numberConversion( 'MCMXCIV' )` | 1994 | M = 1000, CM = 900, XC = 90 and IV = 4. |

</details>