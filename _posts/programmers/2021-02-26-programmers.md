---
title: "programmers [문자열 내림차순으로 배치하기]"
excerpt: "programmers [문자열 내림차순으로 배치하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-26
last_modified_at: 2021-02-26
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

<br>

## 제한 사항

> str은 길이 1 이상인 문자열입니다.

<br>

## 입출력 설명

입출력 예

|s|return|
|------|---|
|Zbcdefg|gfedcbZ|

<br>

```js
import java.util.*;

class Solution {
    public String solution(String s) {
        char[] chars = s.toCharArray();
        Arrays.sort(chars);
        return new StringBuffer(new String(chars)).reverse().toString();
    }
}
```

```js
function solution(s) {
    return s.split("").sort().reverse().join('');
}
```
