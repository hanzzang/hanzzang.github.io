---
title: "programmers [없는 숫자 더하기]"
excerpt: "programmers [없는 숫자 더하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2022-04-08
last_modified_at: 2022-04-08
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 numbers가 매개변수로 주어집니다. numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 return 하도록 solution 함수를 완성해주세요.

<br>

## 제한사항

> 1 ≤ numbers의 길이 ≤ 9<br>
> 0 ≤ numbers의 모든 원소 ≤ 9<br>
> numbers의 모든 원소는 서로 다릅니다.

<br>

## 입출력 예제

입출력 예

|numbers|result|
|------|------|
|[1,2,3,4,6,7,8,0]|14|
|[5,8,4,0,6,7,9]|6|

<br>

예제 #1 <br>

5, 9가 numbers에 없으므로, 5 + 9 = 14를 return 해야 합니다.

<br>

예제 #2 <br>

1, 2, 3이 numbers에 없으므로, 1 + 2 + 3 = 6을 return 해야 합니다.

<br>

```js
import java.util.*;

class Solution {
    public int solution(int[] numbers) {
        int answer = -1;
        
        return answer = 45 - Arrays.stream(numbers).sum();
    }
}
```
