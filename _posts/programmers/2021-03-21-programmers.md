---
title: "programmers [시저 암호]"
excerpt: "programmers [시저 암호]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-03-21
last_modified_at: 2021-03-21
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.

<br>

## 제한 사항

> 공백은 아무리 밀어도 공백입니다.<br>
s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.<br>
s의 길이는 8000이하입니다.<br>
n은 1 이상, 25이하인 자연수입니다.

<br>

## 입출력 설명

입출력 예

|s|n|result|
|------|---|---|
|"AB"|1|"BC"|
|"z"|1|"a"|
|"a B z"|4|"e F d"|

<br>

```js
import java.util.*;

class Solution {
    public String solution(String s, int n) {
        String answer = "";
        int bowl = 0;
        
        for(int i = 0; i < s.length(); i++){
            bowl = (int)s.charAt(i);
            
            if(bowl >= 97 && bowl <= 122){
                bowl += n;
                if(bowl > 122) bowl -= 26;
            }else if(bowl >= 65 && bowl <= 90){
                bowl += n;
                if(bowl > 90) bowl -= 26;
            }else bowl = 32;
            
            answer += (char)bowl;
        }
        return answer;
    }
}
```

```js
function solution(s, n) {
    let answer = '';
    let bowl = 0;
    for(let i = 0; i < s.length; i++){
        bowl = parseInt(s.charCodeAt(i));
        if(bowl > 64 && bowl < 91){
            bowl += n;
            if(bowl > 90) bowl -= 26;
        }else if(bowl > 96 && bowl < 123){
            bowl += n;
            if(bowl > 122) bowl -= 26;
        }else{
            bowl = 32;
        }
        answer += String.fromCharCode(parseInt(bowl));
    }
    return answer;
}
```
