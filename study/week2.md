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
{code}

#### 김지훈

{code}

#### 이소은

```javascript
var lemonadeChange = function(bills) {
    const new_map = {};
    let status = false;
    
    for(let i = 0; i < bills.length; i++) {
        if (bills[i] === 5) {
            if (new_map.hasOwnProperty(5)) {
                new_map[5] += 1
            } else {
                new_map[5] = 1
            }
            status = true
        } else if(bills[i] === 10) {
            if (new_map.hasOwnProperty(10)) {
                new_map[10] += 1
            } else {
                new_map[10] = 1
            }

            if (new_map.hasOwnProperty(5) && new_map[5] > 0 ) {
                new_map[5] -= 1
                status = true
            } else {
                status = false
                break;
            }

        } else if(bills[i] === 20) {
            if (new_map.hasOwnProperty(10) && new_map[10] > 0) {
                new_map[10] -= 1
                if (new_map.hasOwnProperty(5) && new_map[5] > 0) {
                    new_map[5] -= 1
                    status = true
                } else {
                    status = false
                    break;
                }  
            } else {
                if (new_map.hasOwnProperty(5) && new_map[5] > 2) {
                    new_map[5] -= 3
                    status = true
                } else {
                    status = false
                    break;
                }  
            }

            
        }
    }
    
    return status
};
```



## Round 2
### Problem - [744. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)


#### 고은정

{code}

#### 서경원
{code}

#### 김지훈
{code}

#### 이소은

```javascript
var nextGreatestLetter = function(letters, target) {
    const new_map = {}
    for(let i =0; i < letters.length; i++) {
        new_map[letters[i]] = letters[i].charCodeAt(0) - target.charCodeAt(0))
    }
    
    let min_value;
    let find_value = ""
    Object.keys(new_map).forEach((d) => {
        if (!min_value && new_map[d] > 0) {
            min_value = new_map[d]
            find_value = d
        } else {
            if (new_map[d] > 0 && min_value >  new_map[d]) {
                find_value = d
            }
        }
        
    })
    
    if (find_value === "") {
        return letters[0]
    }
    
    return find_value
};
```



## Round 3

### Problem - [326. Power of Three](https://leetcode.com/problems/power-of-three/)



#### 고은정

{code}

#### 서경원

{code}

#### 김지훈

{code}

#### 이소은

```javascript
var isPowerOfThree = function(n) {
    if (n <  1) {
        return false
    } else if (n === 1) {
        return true
    }
    
    return _isPowerOfThree(n);
    
};

var _isPowerOfThree = function(n) {
    
    if (n < 4) {
        return n % 3 === 0
    }
    n = n / 3;
    if (Number(n) === n && n % 1 !== 0) {
        return false
    }
    return _isPowerOfThree(n)
}
```



## Retrospective

