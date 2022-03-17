---
title: "programmers [나누어 떨어지는 숫자 배열]"
excerpt: "programmers [나누어 떨어지는 숫자 배열]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-22
last_modified_at: 2021-02-22
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.<br>
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

<br>

## 제한 사항

> arr은 자연수를 담은 배열입니다.<br>
정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.<br>
divisor는 자연수입니다.<br>
array는 길이 1 이상인 배열입니다.

<br>

## 입출력 설명

입출력 예

|arr|divisor|return|
|------|---|---|
|[5, 9, 7, 10]|5|[5, 10]|
|[2, 36, 1, 3]|1|[1, 2, 3, 36]|
|[3,2,6]|10|[-1]|

<br>

예제 #1 <br>

arr의 원소 중 5로 나누어 떨어지는 원소는 5와 10입니다. 따라서 [5, 10]을 리턴합니다.

<br>

예제 #2 <br>

arr의 모든 원소는 1으로 나누어 떨어집니다. 원소를 오름차순으로 정렬해 [1, 2, 3, 36]을 리턴합니다.

<br>

예제 #3 <br>

3, 2, 6은 10으로 나누어 떨어지지 않습니다. 나누어 떨어지는 원소가 없으므로 [-1]을 리턴합니다.

<br>

```js
import java.util.*;

class Solution {
    public int[] solution(int[] arr, int divisor) {
        int[] answer = {-1};
        int cnt = 0;
        for(int i = 0; i < arr.length; i++){
            if(arr[i]%divisor > 0){
                arr[i] = 0;
                cnt++;
            }
        }
        if(cnt == arr.length) return answer;
        else return Arrays.stream(arr).filter(a -> a != 0).sorted().toArray();
    }
}
```

```js
function solution(arr, divisor) {
    var answer = [];
    
    answer = arr.filter(a => a%divisor == 0).sort((a ,b) => a - b);
    
    if(answer.length == 0){
        answer.push(-1);
    }
    
    return answer;
}
```
