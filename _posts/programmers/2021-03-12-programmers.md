---
title: "programmers [문자열을 정수로 바꾸기]"
excerpt: "programmers [문자열을 정수로 바꾸기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-03-12
last_modified_at: 2021-03-12
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

<br>

## 제한 사항

> s의 길이는 1 이상 5이하입니다.<br>
s의 맨앞에는 부호(+, -)가 올 수 있습니다.<br>
s는 부호와 숫자로만 이루어져있습니다.<br>
s는 "0"으로 시작하지 않습니다.

<br>

## 입출력 설명

입출력 예

> 예를들어 str이 "1234"이면 1234를 반환하고, "-1234"이면 -1234를 반환하면 됩니다.
str은 부호(+,-)와 숫자로만 구성되어 있고, 잘못된 값이 입력되는 경우는 없습니다.

<br>

```js
class Solution {
    public int solution(String s) {
        int answer = 0;;
        return answer = Integer.parseInt(s);
    }
}
```

```js
function solution(s) {
    var answer = parseInt(s);
    return answer;
}
```
