3회차 스터디
2020.2.21

## Round 1
### Problem - [205. Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

#### 고은정
```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isIsomorphic = function(s, t) {
    if(s.length !== t.length) return false;
    if(s === t) return true;
    
    const sdic = {}
    const tdic = {}
    
    for(let i=0; i<s.length; i++){
        if(!sdic.hasOwnProperty(s[i])){
            sdic[s[i]] = Object.keys(sdic).length
        }
        if(!tdic.hasOwnProperty(t[i])){
            tdic[t[i]] = Object.keys(tdic).length        
        }      
        if(sdic[s[i]] !== tdic[t[i]]){
            return false;
        }
    }
    return true;
};
```
- 의외로 안풀려서 한참 고민했던 문제. easy보단 medium 정도로 느꼈다. 실제로 정답률이 별로 높지 않음.
- python에서 set을 사용하면 한줄에 풀 수 있음. python이 포기하기엔 너무 편한 건 사실인 듯...

#### 김지훈
{code}

#### 이소은
{code}

#### 서경원
```java
class Solution {
    public boolean isIsomorphic(String s, String t) {
        return change(s).equals(change(t));
    }
    
    public String change(String s) {
        int c = 0;
        Map<Character, Integer> map = new HashMap<>();
        StringBuilder sb = new StringBuilder();
        for (char ch : s.toCharArray()) {
            Integer v = map.get(ch);
            if (v == null) {
                v = c++;
                map.put(ch, v);
            }
            sb.append(v);
        }
        return sb.toString();
    };
}
```

## Round 2
### Problem - [Word Pattern](https://leetcode.com/problems/word-pattern/)

#### 고은정
```javascript
/**
 * @param {string} pattern
 * @param {string} str
 * @return {boolean}
 */
var wordPattern = function(pattern, str) {
    const wd = str.split(" ")
    if(pattern.length !== wd.length) return false;

    const dic = {}
    const wdic = {}
    
    for(let i=0; i<pattern.length; i++){
        if(!dic.hasOwnProperty(pattern[i])){
            dic[pattern[i]] = Object.keys(dic).length;
        }
        if(!wdic.hasOwnProperty(wd[i])){
            wdic[wd[i]] = Object.keys(wdic).length;
        }
        if(dic[pattern[i]] !== wdic[wd[i]]){
            return false;
        }
    }
    return true;    
};
```
- 처음에 이 문제를 먼저 도전했다가 비슷한 문제에 더 쉬워 보이는 게 있어서 1번 문제로 선정
- Hard 난이도인 Word Pattern 2는 결제해야 해서 더 어려운 것을 원한다면...

#### 김지훈
{code}

#### 이소은
{code}

#### 서경원
```java
class Solution {
    public boolean wordPattern(String pattern, String str) {
        Map<Character, String> chToStr = new HashMap<>();
        Map<String, Character> strToCh = new HashMap<>();
        int len = pattern.length();
        char[] chs = pattern.toCharArray();
        String[] strs = str.split(" ");
        if (len != strs.length) {
            return false;
        }
        
        for (int i = 0 ;i < len ; i++) {
            String s = chToStr.get(chs[i]);
            Character c = strToCh.get(strs[i]);
            if (s == null && c == null) {
                chToStr.put(chs[i], strs[i]);
                strToCh.put(strs[i], chs[i]);
            } else if ((s == null || c == null) || !(s.equals(strs[i]) && c.equals(chs[i]))) {
                return false;
            }
        }

        return true;
    }
}
```

## Retrospective
### 고은정
- 확실히 알고리즘은 꾸준히 풀어주는게 좋은 것 같습니다. 당장 면접을 보든 안보든 2주에 한번 정도는 이지~미디움 난이도를 푸는 게 좋다고 느끼네요.
### 서경원
### 김지훈
### 이소은
