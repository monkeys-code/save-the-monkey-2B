# 2회차 스터디
2020.2.9

## Round 1
### Problem - [860. Lemonade Change](https://leetcode.com/problems/lemonade-change/)



#### 고은정

```python
class Solution:
    def lemonadeChange(self, bills: List[int]) -> bool:
        income = [0,0]
        for b in bills:
            if b == 5:
                income[0] += 5
            if b == 10:
                if income[0] >= 5:
                    income[0] -= 5
                    income[1] += 10
                else:
                    return False
            if b == 20:
                if income[0] >= 5 and income[1] >= 10:
                    income[0] -= 5
                    income[1] -= 10
                elif income[0] >= 15:
                    income[0] -= 15
                else:
                    return False
        return True
```
- 문제를 잘 읽어야 함...

#### 서경원
```javascript
/**
 * @param {number[]} bills
 * @return {boolean}
 */
var lemonadeChange = function(bills) {
    let bill5 = 0;
    let bill10 = 0;
    
    for (let bill of bills) {
        if (bill === 5) {
            bill5++;
        } else if (bill === 10) {
            if (bill5 > 0) {
                bill5--;
                bill10++;
            } else {
                return false;
            }
        } else {
            if (bill10 > 0 && bill5 > 0) {
                bill10--;
                bill5--;
            } else if (bill5 > 2) {
                bill5 -= 3;
            } else {
                return false;
            }
        }
    }
    
    return true;
};
```

#### 김지훈

{code}

#### 이소은

{code}



## Round 2
### Problem - [744. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)


#### 고은정

```python
class Solution:
    def nextGreatestLetter(self, letters: List[str], target: str) -> str:
		for i,v in enumerate(letters): # O(n)
            if target < v:
                return v

        return letters[0]
```

#### 서경원
```javascript
/**
 * @param {character[]} letters
 * @param {character} target
 * @return {character}
 */
var nextGreatestLetter = function(letters, target) {
    for (let letter of letters) {
        if (letter > target) {
            return letter;
        }
    }
    return letters[0];
};
```



#### 김지훈
{code}

#### 이소은

{code}



## Round 3

### Problem - [326. Power of Three](https://leetcode.com/problems/power-of-three/)



#### 고은정

{code}

#### 서경원

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfThree = function(n) {
    if (n <= 0) {
        return false;
    }
    while (n > 1) {
        if (n % 3 !== 0) {
            return false;
        }
        n /= 3;
    }
    return true;
};
```

#### 김지훈

{code}

#### 이소은

{code}



## Retrospective

