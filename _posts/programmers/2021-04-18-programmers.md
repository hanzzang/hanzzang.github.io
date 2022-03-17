---
title: "programmers [정수 내림차순으로 배치하기]"
excerpt: "programmers [정수 내림차순으로 배치하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-18
last_modified_at: 2021-04-18
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.

<br>

## 제한 사항

> n은 1이상 8000000000 이하인 자연수입니다.

<br>

## 입출력 설명

입출력 예

|n|result|
|------|---|
|118372|873211|

<br>

```js
import java.util.stream.Collectors;
import java.util.*;

class Solution {
    public long solution(long n) {
        long answer = Long.parseLong(Arrays.stream(String.valueOf(n).split(""))
                                       .sorted((a,b) -> b.compareTo(a))
                                       .collect(Collectors.joining()));
        return answer;
    }
}
```

```js
function solution(n) {
    var answer = parseInt(n.toString().split("").sort((a,b) => b-a).join(""));
    return answer;
}
```
