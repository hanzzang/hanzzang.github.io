---
title: "programmers [약수의 합]"
excerpt: "programmers [약수의 합]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-04-03
last_modified_at: 2021-04-03
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

<br>

## 제한 사항

> n은 0 이상 3000이하인 정수입니다.

<br>

## 입출력 설명

입출력 예

|n|return|
|------|---|
|12|28|
|5|6|

<br>

예제 #1 <br>

12의 약수는 1, 2, 3, 4, 6, 12입니다. 이를 모두 더하면 28입니다.

<br>

예제 #2 <br>

5의 약수는 1, 5입니다. 이를 모두 더하면 6입니다.

<br>

```js
class Solution {
    public int solution(int n) {
        int answer = 0;
        int bowl = (int)Math.sqrt(n);
        if(n > 0){
            for(int i = 1; i <= bowl; i++){
                if(n%i == 0){
                    if(i == n/i) answer += i;
                    else answer += i + (n/i);
                }
            }    
        }
        return answer;
    }
}
```

```js
function solution(n) {
    let answer = 0;
    let bowl = Math.sqrt(n);
    if(n > 0){
        for(let i = 0; i <= bowl; i++){
            if(n%i == 0){
                if(i == n/i) answer += i;
                else answer += i + (n/i);
            }
        }
    }
    return answer;
}
```
