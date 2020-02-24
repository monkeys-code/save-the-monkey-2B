3회차 스터디
2020.2.21

## Round 1
### Problem - [205. Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

#### 고은정
{code}

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

## Round 3
### Problem -

#### 고은정
{code}

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
### 서경원
### 김지훈
### 이소은
