---
title: "programmers [같은 숫자는 싫어]"
excerpt: "programmers [같은 숫자는 싫어]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-02-19
last_modified_at: 2021-02-19
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다. 이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. <br>

예를 들면,
arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.<br>

배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

<br>

## 제한 사항

> 배열 arr의 크기 : 1,000,000 이하의 자연수<br>
배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수

<br>

## 입출력 설명

입출력 예

|arr|answer|
|------|---|
|[1,1,3,3,0,1,1]|[1,3,0,1]|
|[4,4,4,3,3]|[4,3]|

<br>

```js
import java.util.*;

public class Solution {
    public int[] solution(int []arr) {
        int bowl = arr[0];
        Queue queue = new LinkedList();
        
        queue.offer(arr[0]);
        for(int i = 1; i < arr.length; i++){
            if(bowl != arr[i]){
                queue.offer(arr[i]);
            }
            bowl = arr[i];
        }
        
        int[] answer = new int[queue.size()];
        int cnt = 0;
        while(queue.size() > 0){
            answer[cnt] = (int)queue.poll();
            cnt++;
        }
        
        return answer;
    }
}
```

```js
function solution(arr){
    var answer = [];
    let trust = true;
    for(let i = 0; i < arr.length - 1; i++){
        if(arr[i] != arr[i+1]){
            answer.push(arr[i]);
            trust = true;
        }else{
            trust = false;
        }
    }
    answer.push(arr[arr.length - 1]);
    
    return answer;
}
```
