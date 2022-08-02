---
title: "programmers [모의고사]"
excerpt: "programmers [모의고사]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-01-22
last_modified_at: 2021-01-22
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.<br>

1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...<br>
2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...<br>
3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...<br>

1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.

<br>

## 제한 사항

> 시험은 최대 10,000 문제로 구성되어있습니다.<br>
문제의 정답은 1, 2, 3, 4, 5중 하나입니다.<br>
가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.

<br>

## 입출력 설명

입출력 예

> answers return<br>
[1,2,3,4,5][1]<br>
[1,3,2,4,2][1,2,3]

<br>

예제 #1 <br>

수포자 1은 모든 문제를 맞혔습니다.<br>
수포자 2는 모든 문제를 틀렸습니다.<br>
수포자 3은 모든 문제를 틀렸습니다.<br>
따라서 가장 문제를 많이 맞힌 사람은 수포자 1입니다.

<br>

예제 #2 <br>

모든 사람이 2문제씩을 맞췄습니다.

<br>

```js
import java.util.*;

class Solution {
    public int[] solution(int[] answers) {
        int[] answer ={};
        int [] A = {1,2,3,4,5}; //1번 수포자
        int [] B = {2,1,2,3,2,4,2,5}; //2번 수포자
        int [] C = {3,3,1,1,2,2,4,4,5,5}; //3번 수포자
        int[] ans ={0,0,0};
        int i;

        ArrayList<Integer> fin = new ArrayList<Integer>();

        //채점 단계
        for(i=0;i<answers.length;i++){
            if(answers[i] == A[i % 5]) ans[0]++;
        }
        for(i=0;i<answers.length;i++){
            if(answers[i] == B[i % 8]) ans[1]++;
        }
        for(i=0;i<answers.length;i++){
            if(answers[i] == C[i % 10]) ans[2]++;
        }

        //max는 가장 많이 문제를 맞춘 사람의 맞춘 개수?    
        int max = Math.max(ans[0], Math.max(ans[1], ans[2]));

        //max 가지고 있는 개수 
        for(i=0;i<3;i++) {
            if(ans[i] == max) fin.add(i+1);
        }

        int t=0;
        answer = new int[fin.size()];
        if(ans[0]== max) answer[t++]=1;
        if(ans[1]== max) answer[t++]=2;
        if(ans[2]== max) answer[t++]=3;
        return answer;
    }
}
```

```js
function solution(answers) {
    var answer = [];
    var a1 = [1, 2, 3, 4, 5];
    var a2 = [2, 1, 2, 3, 2, 4, 2, 5]
    var a3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5];
  
    //채점 단계
    var a1c = answers.filter((a,i)=> a === a1[i%a1.length]).length;
    var a2c = answers.filter((a,i)=> a === a2[i%a2.length]).length;
    var a3c = answers.filter((a,i)=> a === a3[i%a3.length]).length;
  
    //max는 가장 많이 문제를 맞춘 사람의 맞춘 개수?  
    var max = Math.max(a1c,a2c,a3c);
  
    //max 가지고 있는 개수 
    if (a1c === max) {answer.push(1)};
    if (a2c === max) {answer.push(2)};
    if (a3c === max) {answer.push(3)};

    return answer;
}
```
