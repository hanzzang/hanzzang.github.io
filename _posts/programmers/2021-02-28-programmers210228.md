---
title: "programmers [서울에서 김서방 찾기]"
excerpt: "programmers [서울에서 김서방 찾기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-28
last_modified_at: 2021-02-28
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

String형 배열 seoul의 element중 Kim의 위치 x를 찾아, 김서방은 x에 있다는 String을 반환하는 함수, solution을 완성하세요. seoul에 Kim은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

<br>

## 제한 사항

> seoul은 길이 1 이상, 1000 이하인 배열입니다.<br>
seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.<br>
Kim은 반드시 seoul 안에 포함되어 있습니다.

<br>

## 입출력 설명

입출력 예

|seoul|return|
|------|---|
|[Jane, Kim]|김서방은 1에 있다|

<br>

```js
import java.util.*;

class Solution {
    public String solution(String[] seoul) {
        int answer = new StringBuffer(seoul).indexOf("Kim");
        return "김서방은 " + answer + "에 있다";
    }
}
```

```js
function solution(seoul) {
    var answer = seoul.indexOf("Kim");
    return "김서방은 " + answer + "에 있다";
}
```
