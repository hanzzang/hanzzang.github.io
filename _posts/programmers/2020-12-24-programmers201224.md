---
title: "programmers [완주하지 못한 선수]"
excerpt: "programmers [완주하지 못한 선수]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2020-12-24
last_modified_at: 2020-12-24
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

수많은 마라톤 선수들이 마라톤에 참여하였습니다.
단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

<br>

## 제한 사항

> 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다. <br>
completion의 길이는 participant의 길이보다 1 작습니다.<br>
참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.<br>
참가자 중에는 동명이인이 있을 수 있습니다.

<br>

## 입출력 설명

예제 #1
leo는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

예제 #2
vinko는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

예제 #3
mislav는 참여자 명단에는 두 명이 있지만, 완주자 명단에는 한 명밖에 없기 때문에 한명은 완주하지 못했습니다.

```js
import java.util.Arrays;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        Arrays.sort(participant);
        Arrays.sort(completion);
        for(int i = 0; i < completion.length; i++){
            if(!completion[i].equals(participant[i])) return answer = participant[i];
        }
        return answer = participant[completion.length];
    }
}
// O(n2)로 인한 효율성 실패
function solution(participant, completion) {
    for(var i = 0; i < completion.length; i++){
    	//indexOf의 경우 반복문의 해당
        participant.splice(participant.indexOf(completion[i]),1);
    }
    return participant[0];
}

// O(n)로 최종 통과
function solution(participant, completion) {
    participant.sort();
    completion.sort();
    for(let i in completion){
        if(participant[i] != completion[i]) return participant[i];
    }
    return participant[completion.length];
}
```