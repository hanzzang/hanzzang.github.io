---
title: "programmers [자릿수 더하기]"
excerpt: "programmers [자릿수 더하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-11
last_modified_at: 2021-04-11
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

<br>

## 제한 사항

> N의 범위 : 100,000,000 이하의 자연수

<br>

## 입출력 설명

입출력 예

|N|answer|
|------|---|
|123|6|
|987|24|

<br>

예제 #1 <br>

문제의 예시와 같습니다.

<br>

예제 #2 <br>

9 + 8 + 7 = 24이므로 24를 return 하면 됩니다.

<br>

```js
import java.util.Arrays;
import java.util.stream.Stream;

public class Solution {
    public int solution(int n) {
        int answer = Stream.of(String.valueOf(n).split("")).mapToInt(Integer::parseInt).sum();
        return answer;
    }
}
```

```js
function solution(n){
    var answer = n.toString().split("").reduce((a,b) => parseInt(a) + parseInt(b), 0);
    return answer;
}
```
