---
title: "programmers [소수 찾기]"
excerpt: "programmers [소수 찾기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-03-02
last_modified_at: 2021-03-02
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

1부터 입력받은 숫자 n 사이에 있는 소수의 개수를 반환하는 함수, solution을 만들어 보세요.<br>

소수는 1과 자기 자신으로만 나누어지는 수를 의미합니다.
(1은 소수가 아닙니다.)

<br>

## 제한 사항

> n은 2이상 1000000이하의 자연수입니다.

<br>

## 입출력 설명

입출력 예

|n|result|
|------|---|
|10|4|
|5|3|

<br>

예제 #1 <br>

1부터 10 사이의 소수는 [2,3,5,7] 4개가 존재하므로 4를 반환

<br>

예제 #2 <br>

1부터 5 사이의 소수는 [2,3,5] 3개가 존재하므로 3를 반환

<br>

```js
import java.util.*;

class Solution {
    public int solution(int n) {
        int[] answer = new int[n + 1];
        answer[0] = 1;
        answer[1] = 1;
        
        for(int i = 2; i < Math.sqrt(n) + 1; i++){
            for(int j = 2*i; j < n + 1; j+=i){
                answer[j] = 1;
            }
        }
        return Math.toIntExact(Arrays.stream(answer).filter(a -> a != 1).count());
    }
}
```

```js
function solution(n) {
    const answer = new Array();
    
    for(let i = 0; i < n + 1; i++){
        answer.push(i);
    }
    answer[0] = -1;
    answer[1] = -1;
    
    for(let j = 2; j < Math.sqrt(answer.length); j++){
        for(let k = 2*j; k < n + 1; k += j){
            answer[k] = -1;
        }
    }
    return answer.filter(a => a != -1).length;
}
```
