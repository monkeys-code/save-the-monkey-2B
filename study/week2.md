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

{code}



## Round 2
### Problem - [744. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)


#### 고은정

{code}

#### 서경원
{code}

#### 김지훈
{code}

#### 이소은

{code}



## Round 3

### Problem - [326. Power of Three](https://leetcode.com/problems/power-of-three/)



#### 고은정

{code}

#### 서경원

{code}

#### 김지훈

{code}

#### 이소은

{code}



## Retrospective

