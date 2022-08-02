---
title: "programmers [짝수와 홀수]"
excerpt: "programmers [짝수와 홀수]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-05-01
last_modified_at: 2021-05-01
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

<br>

## 제한 사항

> num은 int 범위의 정수입니다.<br>
0은 짝수입니다.

<br>

## 입출력 설명

입출력 예

|num|return|
|------|---|
|3|"Odd"|
|4|"Even"|

<br>

```js
class Solution {
    public String solution(int num) {
        return num%2 == 0 ? "Even" : "Odd";
    }
}
```

```js
function solution(num) {
    return num%2 == 0 ? "Even" : "Odd";
}
```
