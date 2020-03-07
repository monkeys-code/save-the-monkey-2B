6회차 스터디
2020.3.6

## Round 1
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

#### 고은정
```javascript
var maxProfit = function(prices) {
    
    let net = 0;

    for(let i=0; i<prices.length-1; i++){
        for(let j=i+1; j<prices.length; j++){
            if(prices[i] <prices[j]){
                if(net < prices[j] - prices[i]){
                    net = prices[j] - prices[i]
                }
            }
        }        
    }
    return net;    
};
```

#### 김지훈
```javascript
```

#### 이소은
```javascript

var maxProfit = function(prices) {
    let index = 0
    let min = 2 ** 32
    let max = 0
    
    if (prices.length <= 1) {
        return 0
    }
    
    while(index < prices.length) {
        
        if (min > prices[index]) {
            min = prices[index]
            
        } else if (prices[index] - min > max) {
            max = prices[index] - min
        }
       
        index++
        
    }
    
    return max
    
};
```

#### 서경원
```java
class Solution {
    public int maxProfit(int[] prices) {
        int len = prices.length;
        int maxDiff = 0;
        for (int i = 0 ; i < len ; i++) {
            for (int j = i + 1 ; j < len ; j++) {
                int profit = prices[j] - prices[i];
                if (profit > maxDiff) {
                    maxDiff = profit;
                }
            }
        }
        return maxDiff;
    }
}

```

## Round 2
### https://www.acmicpc.net/problem/1197

#### 고은정
```javascript

```

#### 김지훈
```javascript

```

#### 이소은
```
```

#### 서경원
```java

```

## Retrospective
### 고은정
### 서경원
### 김지훈
### 이소은
