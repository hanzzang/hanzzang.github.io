---
title: "programmers [직사각형 별찍기]"
excerpt: "programmers [직사각형 별찍기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2022-01-08
last_modified_at: 2022-01-08
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
별(*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

<br>

## 제한 사항

> n과 m은 각각 1000 이하인 자연수입니다.

<br>

```js
import java.util.Scanner;
import java.util.stream.IntStream;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        
        StringBuffer sb = new StringBuffer();
        
        IntStream.range(0,a).forEach(s -> sb.append("*"));
        IntStream.range(0,b).forEach(s -> System.out.println(sb));
    }
}
```
