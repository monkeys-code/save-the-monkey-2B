# 1회차 스터디
2020. 01. 18
진행자 김지훈

## Round 1
### Problem - [Two Sum](https://leetcode.com/problems/two-sum/)
```
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

---
Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

#### 고은정
{image}
{code}
{retrospective}

#### 서경원
{image}

##### Code
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const len = nums.length;
    for (let i = 0 ; i < len ; i++) {
        for (let j = i + 1 ; j < len ; j++) {
            if (nums[i] + nums[j] === target) {
                return [i, j];
            }
        }
    }
    return [];
};
```

#### 김지훈
{purpose}
{solution}

## Round 2
### Problem - [Palindrom Number](https://leetcode.com/problems/palindrome-number/)
```
Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

---
Example 1:

Input: 121
Output: true
---
Example 2:

Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
---
Example 3:

Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
---
Follow up
:: Coud you solve it without converting the integer to a string?
```

#### 고은정
{image}
{code}
{retrospective}

#### 서경원
{image}

##### Code

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
    if (x < 0) {
        return false;
    } else if (x < 10) {
        return true;
    }
    
    const str = x.toString();
    const len = str.length;
    const last = len - 1;
    const half = Math.floor(len / 2);
    for (let i = 0 ; i < half ; i++) {
        if (str[i] !== str[last - i]) {
            return false;
        }
    }
    return true;
};
```

##### Retrospective
- 오랜만에 시작하니 감을 많이 잃은 것 같다.
- 다시 처음부터 한다는 마음가짐으로 진행해야할 것 같다.
- 한 문제를 풀 때 다양한 시각으로 보는 연습이 필요하다.

#### 김지훈
{purpose}
{solution}

## Retrospective
* 오랫만에 하려니까 정말 쉽지 않다.
* 같은 문제를 다른 언어로 풀어보는게 어느정도 도움이 되는 것 같다.
* 작년에 한거 다 까먹은 것 같다.
