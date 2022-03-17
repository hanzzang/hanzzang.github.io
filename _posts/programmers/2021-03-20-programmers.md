---
title: "programmers [내적]"
excerpt: "programmers [내적]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-03-20
last_modified_at: 2021-03-20
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

길이가 같은 두 1차원 정수 배열 a, b가 매개변수로 주어집니다. a와 b의 내적을 return 하도록 solution 함수를 완성해주세요.<br>

이때, a와 b의 내적은 a[0]b[0] + a[1]b[1] + ... + a[n-1]*b[n-1] 입니다. (n은 a, b의 길이)

<br>

## 제한 사항

> a, b의 길이는 1 이상 1,000 이하입니다.<br>
a, b의 모든 수는 -1,000 이상 1,000 이하입니다.

<br>

## 입출력 설명

입출력 예

|a|b|result|
|------|---|---|
|[1,2,3,4]|[-3,-1,0,2]|3|
|[-1,0,1]|[1,0,-1]|-2|

<br>

```js
class Solution {
    public int solution(int[] a, int[] b) {
        int answer = 0;
        for(int i = 0; i < a.length; i++){
            answer += a[i]*b[i];
        }
        return answer;
    }
}
```

```js
function solution(a, b) {
    let answer = 0;
    for(let i = 0; i < a.length; i++){
        answer += a[i]*b[i];
    }
    return answer;
}
```
