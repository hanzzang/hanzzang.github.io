---
title: "programmers [평균 구하기]"
excerpt: "programmers [평균 구하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-05-09
last_modified_at: 2021-05-09
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

<br>

## 제한 사항

> arr은 길이 1 이상, 100 이하인 배열입니다.<br>
arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

<br>

## 입출력 설명

입출력 예

|arr|return|
|------|---|
|[1,2,3,4]|2.5|
|[5,5]|5|

<br>

```js
import java.util.stream.IntStream;

class Solution {
    public double solution(int[] arr) {
        double answer = IntStream.of(arr).average().getAsDouble();
        return answer;
    }
}
```

```js
function solution(arr) {
    var answer = arr.reduce((a, b) => a+b, 0)/arr.length;
    return answer;
}
```
