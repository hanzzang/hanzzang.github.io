---
title: "programmers [가운데 글자 가져오기]"
excerpt: "programmers [가운데 글자 가져오기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-18
last_modified_at: 2021-02-18
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

<br>

## 제한 사항

> s는 길이가 1 이상, 100이하인 스트링입니다.

<br>

## 입출력 설명

입출력 예

|s|return|
|------|---|
|abcde|c|
|qwer|we|

<br>

```js
class Solution {
    public String solution(String s) {
        String answer = "";
        
        return answer = s.substring(s.length() / 2 - (1 - (s.length() % 2)), s.length() / 2 - (1 - (s.length() % 2)) + (2 - s.length() % 2));
    }
}
```

```js
function solution(s) {
    var answer = '';
    return answer = s.substring(s.length/2 - (1 - s.length%2), s.length/2 + (2 - s.length%2) - (1 - s.length%2));
}
```
