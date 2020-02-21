# 2회차 스터디
2020.2.9

## Round 1
### Problem - [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)


#### 고은정

{code}

#### 김지훈

{code}

#### 이소은

{code}

### Solution

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    const matchMap = {
        '{': '}',
        '(': ')',
        '[': ']',
    };
    const stack = [];
    for (let c of s) {
        switch (c) {
            case '{': case '(': case '[':
                stack.push(c);
                break;
            default:
                if (c !== matchMap[stack.pop()]) {
                    return false;
                }
        }
    }
    return stack.length === 0;
};
```

## Round 2
### Problem - [190. Reverse Bits](https://leetcode.com/problems/reverse-bits/)


#### 고은정

{code}

#### 김지훈

{code}

#### 이소은

{code}

### Solution

#### with Bitwise Operators (Java)

```java
public class Solution {
    // you need treat n as an unsigned value
    public int reverseBits(int n) {
        int result = 0;
        for (int i = 0 ; i < 32 ; i++) {
            result = (result << 1) | (n & 1);
            n = n >> 1;
        }
        return result;
    }
}
```

#### with Arithmetic Operators (JavaScript)

```javascript
/**
 * @param {number} n - a positive integer
 * @return {number} - a positive integer
 */
var reverseBits = function(n) {
    let result = 0;
    for (let i = 0 ; i < 32 ; i++) {
        result = (result << 2) + (n % 2);
        n = Math.floor(n / 2);
    }
    return result;
};
```

## Round 3

### Problem - 


#### 고은정

{code}

#### 김지훈

{code}

#### 이소은

{code}


### Solution

```javascript
/**
 * @param {number} n
 * @return {string[]}
 */
var generateParenthesis = function(n) {
    const result = [];
    recu(n, n, '', result);
    return result;
};

function recu(opens, closes, text, result) {
    if (opens === 0) {
        result.push(text + ')'.repeat(closes));
    } else if (opens <= closes) {
        recu(opens - 1, closes, text + '(', result);
        recu(opens, closes - 1, text + ')', result);
    }
}

```

## Retrospective

#### 고은정


#### 서경원


#### 김지훈
* 수학문제를 만나 멘탈이 바사삭
* 그래도 시간 체크하면서, 문제를 풀어나갔어야 했다.
    * 가끔 면접장에서 어떻게 접근해야 하는지 모르겠는 문제가 가끔 나옴
    * 멘탈 바사삭을 대비합시다

#### 이소은

