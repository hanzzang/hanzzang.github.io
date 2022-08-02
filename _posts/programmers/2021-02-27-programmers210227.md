---
title: "programmers [문자열 다루기 기본]"
excerpt: "programmers [문자열 다루기 기본]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-27
last_modified_at: 2021-02-27
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 a234이면 False를 리턴하고 1234라면 True를 리턴하면 됩니다.

<br>

## 제한 사항

> s는 길이 1 이상, 길이 8 이하인 문자열입니다.

<br>

## 입출력 설명

입출력 예

|s|return|
|------|---|
|a234|false|
|1234|true|

<br>

```js
import java.util.*;

class Solution {
    public boolean solution(String s) {
        boolean answer = s.length() == 4 || s.length() == 6;
        int bowl = 0;
        for(int i = 0; i < s.length(); i++){
            try{
                bowl = Integer.parseInt(s.substring(i, i+1));
            }catch(Exception e){
                return false;
            }
        }
        return answer;
    }
}
```

```js
function solution(s) {
    var answer = s.length == 4 || s.length == 6;
    for(let i = 0; i < s.length; i++){
        if(isNaN(parseInt(s.substr(i, 1)))){
            return false;
        }
    }
    return answer;
}
```
