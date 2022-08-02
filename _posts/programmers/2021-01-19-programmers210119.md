---
title: "programmers [K번째수]"
excerpt: "programmers [K번째수]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-01-19
last_modified_at: 2021-01-19
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다. <br>

예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면 <br>

array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다. <br>
1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다. <br>
2에서 나온 배열의 3번째 숫자는 5입니다. <br>

배열 array, [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 return 하도록 solution 함수를 작성해주세요.

<br>

## 제한 사항

> array의 길이는 1 이상 100 이하입니다.<br>
array의 각 원소는 1 이상 100 이하입니다.<br>
commands의 길이는 1 이상 50 이하입니다.<br>
commands의 각 원소는 길이가 3입니다.

<br>

## 입출력 설명

입출력 예

> array commands return <br>
[1, 5, 2, 6, 3, 7, 4][2, 5, 3], [4, 4, 1], [1, 7, 3] [5, 6, 3]

<br>

입출력 예 설명 <br>

> [1, 5, 2, 6, 3, 7, 4]를 2번째부터 5번째까지 자른 후 정렬합니다. [2, 3, 5, 6]의 세 번째 숫자는 5입니다.<br>
[1, 5, 2, 6, 3, 7, 4]를 4번째부터 4번째까지 자른 후 정렬합니다. [6]의 첫 번째 숫자는 6입니다.<br>
[1, 5, 2, 6, 3, 7, 4]를 1번째부터 7번째까지 자릅니다. [1, 2, 3, 4, 5, 6, 7]의 세 번째 숫자는 3입니다.

<br>

```js
import java.util.*;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        int[] bowl = {};
        int bowlCnt = 0;
        for(int i = 0; i < commands.length; i++){
            bowl = new int[commands[i][1] - commands[i][0] + 1];
            for(int j = commands[i][0] - 1; j < commands[i][1]; j++){
                bowl[bowlCnt] = array[j];
                bowlCnt++;
            }
            Arrays.sort(bowl);
            answer[i] = bowl[commands[i][2] - 1];
            bowlCnt = 0;
        }
        return answer;
    }
}
```

```js
function solution(array, commands) {
    let answer = [];
    let bowl = [];
    let cnt = 0;
    while(cnt < commands.length){
        for(let i = commands[cnt][0] - 1; i < commands[cnt][1]; i++){
           bowl.push(array[i]);
        }
        //숫자는 ASCII 코드 순서로 정렬하기 떄문에 결과값이 생각했던 순서와 다를 수 있다.
        //bowl.sort();
        bowl.sort((a, b) => a-b);
        console.log(bowl);
        answer[cnt] = bowl[commands[cnt][2] - 1];
        bowl = [];
        cnt++;
    }
    
    return answer;
}
```
