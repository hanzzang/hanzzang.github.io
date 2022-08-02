---
title: "programmers [수박수박수박수박수박수?]"
excerpt: "programmers [수박수박수박수박수박수?]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-03-05
last_modified_at: 2021-03-05
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

<br>

## 제한 사항

> n은 길이 10,000이하인 자연수입니다.

<br>

## 입출력 설명

입출력 예

|n|return|
|------|---|
|3|"수박수"|
|4|"수박수박"|

<br>

```js
import java.util.*;

class Solution {
    public String solution(int n) {
        String[] bowl = new String[(int)Math.round((double)n/2)];
        Arrays.fill(bowl, "수박");
        String answer = String.join("", bowl);
        return answer.substring(0,n);
    }
}
```

```js
function solution(n) {
    var answer = [...Array(Math.round(n/2)).fill("수박")];
    return answer.join("").substr(0, n);
}
```
