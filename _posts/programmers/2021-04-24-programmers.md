---
title: "programmers [정수 제곱근 판별]"
excerpt: "programmers [정수 제곱근 판별]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-24
last_modified_at: 2021-04-24
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.<br>

n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

<br>

## 제한 사항

> n은 1이상, 50000000000000 이하인 양의 정수입니다.

<br>

## 입출력 설명

입출력 예

|n|result|
|------|---|
|121|144|
|3|-1|

<br>

예제 #1 <br>

121은 양의 정수 11의 제곱이므로, (11+1)를 제곱한 144를 리턴합니다.

<br>

예제 #2 <br>

3은 양의 정수의 제곱이 아니므로, -1을 리턴합니다.

<br>

```js
class Solution {
    public long solution(long n) {
        long answer = n == Math.pow((int)Math.sqrt(n), 2) ? (long)Math.pow((int)Math.sqrt(n) + 1, 2) : -1;
        return answer;
    }
}
```

```js
function solution(n) {
    var answer = n == Math.pow(parseInt(Math.sqrt(n)), 2) ? Math.pow(parseInt(Math.sqrt(n)) + 1, 2) : -1 ;
    return answer;
}
```
