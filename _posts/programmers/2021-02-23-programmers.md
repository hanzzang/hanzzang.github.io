---
title: "programmers [두 정수 사이의 합]"
excerpt: "programmers [두 정수 사이의 합]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-23
last_modified_at: 2021-02-23
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요.<br>

예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

<br>

## 제한 사항

> a와 b가 같은 경우는 둘 중 아무 수나 리턴하세요.<br>
a와 b는 -10,000,000 이상 10,000,000 이하인 정수입니다.<br>
a와 b의 대소관계는 정해져있지 않습니다.

<br>

## 입출력 설명

입출력 예

|a|b|return|
|------|---|---|
|3|5|12|
|3|3|3|
|5|3|12|

<br>

```js
class Solution {
    
    public long solution(int a, int b) {
        return betweenAandB(Math.min(a, b), Math.max(b, a));
    }

    public long betweenAandB(long min, long max) {
        return (max - min + 1) * (max + min) / 2;
    }
}
```

```js
function solution(a, b) {
    
    var answer = (a + b) * (Math.max(a, b) - Math.min(a, b) + 1)/2;
    
    return answer;
}
```
