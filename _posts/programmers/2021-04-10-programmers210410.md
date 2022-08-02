---
title: "programmers [이상한 문자 만들기]"
excerpt: "programmers [이상한 문자 만들기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-10
last_modified_at: 2021-04-10
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

<br>

## 제한 사항

> 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.<br>
첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

<br>

## 입출력 설명

입출력 예

|s|return|
|------|---|
|"try hello world"|"TrY HeLlO WoRlD"|

<br>

입출력 예 설명 <br>

"try hello world"는 세 단어 "try", "hello", "world"로 구성되어 있습니다. 각 단어의 짝수번째 문자를 대문자로, 홀수번째 문자를 소문자로 바꾸면 "TrY", "HeLlO", "WoRlD"입니다. 따라서 "TrY HeLlO WoRlD" 를 리턴합니다.

<br>

```js
class Solution {
    public String solution(String s) {
        String answer = "";
        String[] bowl = s.split("");
        boolean trust = true;
        for(int i = 0; i < bowl.length; i++){
            if(!" ".equals(bowl[i])){
                if(trust){
                    bowl[i] = bowl[i].toUpperCase();
                    trust = false;
                }else{
                    bowl[i] = bowl[i].toLowerCase();
                    trust = true;
                }
            }else{
                trust = true;
            }
        }
        return answer = String.join("", bowl);
    }
}
```

```js
function solution(s) {
    var answer = s.split("");
    let cnt = 0;
    for(let i = 0; i < answer.length; i++){
        if(answer[i] != " "){
            if(cnt == 0){
                answer[i] = answer[i].toUpperCase();
                cnt++;
            }else{
                answer[i] = answer[i].toLowerCase();
                cnt--;
            }    
        }else{
            cnt = 0;
        }
    }
    return answer.join("");
}
```
