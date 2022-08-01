---
title: "programmers [N개의 최소공배수]"
excerpt: "programmers [N개의 최소공배수]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2022-05-01
last_modified_at: 2022-05-01
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.

<br>

## 제한사항

> arr은 길이 1이상, 15이하인 배열입니다.<br>
> arr의 원소는 100 이하인 자연수입니다.

<br>

## 입출력 예제

입출력 예

|id_list|report|
|------|------|
|[2,6,8,14]|168|
|[1,2,3]|6|

<br>

```js
class Solution {
    public int solution(int[] arr) {
        int answer = arr[0];
        
        for(int i = 1; i < arr.length; i++){
            answer = arr[i] * answer / gcd(arr[i], answer);
        }
        return answer;
    }
    
    public int gcd(int a, int b){
        if(b == 0) return a;
        return gcd(b, a % b);
    }
}
```
