---
title: "programmers [자연수 뒤집어 배열로 만들기]"
excerpt: "programmers [자연수 뒤집어 배열로 만들기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-17
last_modified_at: 2021-04-17
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

<br>

## 제한 사항

> n은 10,000,000,000이하인 자연수입니다.

<br>

## 입출력 설명

입출력 예

|n|return|
|------|---|
|12345|[5,4,3,2,1]|

<br>

```js
import java.util.stream.Stream;

class Solution {
    public int[] solution(long n) {
        StringBuffer sb = new StringBuffer(String.valueOf(n));
        int[] answer = Stream.of(String.valueOf(sb.reverse()).split("")).mapToInt(Integer::parseInt).toArray();
        return answer;
    }
}
```

```js
function solution(n) {
    var answer = n.toString().split("").reverse().map(a => parseInt(a));
    return answer;
}
```
