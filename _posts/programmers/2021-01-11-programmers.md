---
title: "programmers [주식가격]"
excerpt: "programmers [주식가격]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-01-11
last_modified_at: 2021-01-11
---

![HAN.jpg](/assets/images/programmers.png)


## 문제 설명

초 단위로 기록된 주식가격이 담긴 배열 prices가 매개변수로 주어질 때, 가격이 떨어지지 않은 기간은 몇 초인지를 return 하도록 solution 함수를 완성하세요.

<br>

## 제한 사항

> prices의 각 가격은 1 이상 10,000 이하인 자연수입니다. <br>
prices의 길이는 2 이상 100,000 이하입니다. <br>

<br>

## 입출력 설명

입출력 예

> prices | return <br>
[1, 2, 3, 2, 3] | [4, 3, 1, 1, 0] <br>

<br>

입출력 예 설명

> 1초 시점의 ₩1은 끝까지 가격이 떨어지지 않았습니다. <br>
2초 시점의 ₩2은 끝까지 가격이 떨어지지 않았습니다. <br>
3초 시점의 ₩3은 1초뒤에 가격이 떨어집니다. 따라서 1초간 가격이 떨어지지 않은 것으로 봅니다. <br>
4초 시점의 ₩2은 1초간 가격이 떨어지지 않았습니다. <br>
5초 시점의 ₩3은 0초간 가격이 떨어지지 않았습니다. <br>

<br>

```js
import java.util.*;

class Solution {
    public int[] solution(int[] prices) {
        //Queue solution
        Queue pricesQueue = new LinkedList();

        for(int price : prices){
            pricesQueue.offer(price);
        }
        
        int[] answer = new int[prices.length];
        int term = 0;
        int answerCnt = 0;
        Object pricesQueuePoll;
        while(!pricesQueue.isEmpty()){
            term = 0;
            pricesQueuePoll = pricesQueue.poll();
            for(int i = answerCnt + 1; i < prices.length; i++){
                if((int)pricesQueuePoll <= prices[i]) term++;
                else{
                    term++;
                    break;   
                }
            }
            answer[answerCnt] = term;
            answerCnt++;
        }
       
        return answer;
    }
}
```