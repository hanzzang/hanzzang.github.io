---
title: "programmers [가장 큰 수]"
excerpt: "programmers [가장 큰 수]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-01-20
last_modified_at: 2021-01-20
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

0 또는 양의 정수가 주어졌을 때, 정수를 이어 붙여 만들 수 있는 가장 큰 수를 알아내 주세요.<br>

예를 들어, 주어진 정수가 [6, 10, 2]라면 [6102, 6210, 1062, 1026, 2610, 2106]를 만들 수 있고, 이중 가장 큰 수는 6210입니다.<br>

0 또는 양의 정수가 담긴 배열 numbers가 매개변수로 주어질 때, 순서를 재배치하여 만들 수 있는 가장 큰 수를 문자열로 바꾸어 return 하도록 solution 함수를 작성해주세요.

<br>

## 제한 사항

> numbers의 길이는 1 이상 100,000 이하입니다.<br>
numbers의 원소는 0 이상 1,000 이하입니다.<br>
정답이 너무 클 수 있으니 문자열로 바꾸어 return 합니다.

<br>

## 입출력 설명

입출력 예

> numbers return<br>
[6, 10, 2] 6210<br>
[3, 30, 34, 5, 9] 9534330

<br>

```js
import java.util.*;

class Solution {
    public String solution(int[] numbers) {
        String answer = "";
        PriorityQueue<String> pq = new PriorityQueue<String>(new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return Integer.parseInt(s2 + s1) - Integer.parseInt(s1 + s2);
            }
        });
        
        for(int i = 0; i < numbers.length; i++){ //우선순위 큐에 정렬
            pq.offer(Integer.toString(numbers[i]));
        }
        
        while(pq.size() > 0){ //정렬된 numbers 더하기
            answer += pq.poll();
        }
        
        if(answer.charAt(0) == '0'){ //numbers의 원소는 0 이상 1,000 이하라서 첫번째 char가 '0'이라면 "0" return
            return "0";
        }
        return answer;
    }
    
}
```

```js
function solution(numbers) {
    let answer = '';
    numbers.sort((s1, s2) => {
        if((s1.toString() + s2.toString()) > (s2.toString() + s1.toString())){
            return -1;
        }else{
            return 1;
        }
    });
    
    for(let str of numbers){
        answer += str;
    }
    
    if(answer.charAt(0) == '0'){
        return "0";
    }
    return answer;
}
```
