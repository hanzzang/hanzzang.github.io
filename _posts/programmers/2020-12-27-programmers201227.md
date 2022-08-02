---
title: "programmers [위장]"
excerpt: "programmers [위장]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2020-12-27
last_modified_at: 2020-12-27
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

스파이들은 매일 다른 옷을 조합하여 입어 자신을 위장합니다.

예를 들어 스파이가 가진 옷이 아래와 같고 오늘 스파이가 동그란 안경, 긴 코트, 파란색 티셔츠를 입었다면 다음날은 청바지를 추가로 입거나 동그란 안경 대신 검정 선글라스를 착용하거나 해야 합니다.

> 종류 | 이름<br>
얼굴 | 동그란 안경, 검정 선글라스<br>
상의 | 파란색 티셔츠<br>
하의 | 청바지<br>
겉옷 | 긴 코트
<br>

스파이가 가진 의상들이 담긴 2차원 배열 clothes가 주어질 때 서로 다른 옷의 조합의 수를 return 하도록 solution 함수를 작성해주세요.

<br>

## 제한 사항

> clothes의 각 행은 [의상의 이름, 의상의 종류]로 이루어져 있습니다.<br>
스파이가 가진 의상의 수는 1개 이상 30개 이하입니다.<br>
같은 이름을 가진 의상은 존재하지 않습니다.<br>
clothes의 모든 원소는 문자열로 이루어져 있습니다.<br>
모든 문자열의 길이는 1 이상 20 이하인 자연수이고 알파벳 소문자 또는 '_' 로만 이루어져 있습니다.<br>
스파이는 하루에 최소 한 개의 의상은 입습니다.<br>

<br>

## 입출력 설명

예제 #1
headgear에 해당하는 의상이 yellow_hat, green_turban이고 eyewear에 해당하는 의상이 blue_sunglasses이므로 아래와 같이 5개의 조합이 가능합니다.

1. yellow_hat <br>
2. blue_sunglasses <br>
3. green_turban <br>
4. yellow_hat + blue_sunglasses <br>
5. green_turban + blue_sunglasses <br>

<br>

예제 #2
face에 해당하는 의상이 crow_mask, blue_sunglasses, smoky_makeup이므로 아래와 같이 3개의 조합이 가능합니다.

1. crow_mask <br>
2. blue_sunglasses <br>
3. smoky_makeup <br>

```js
import java.util.Arrays;
//((한 종류의 이름의 수 + 1(해당 옷을 입지않을 경우의 수)) * (각 종류의 이름의 수 + 1)) -1 (반드시 한 개의 옷은 입어야함)
class Solution {
    public int solution(String[][] clothes) {
        int answer = 1;
        int sameKindOfClothesCnt = 1; // 한 종류의 이름의 수
        clothesSort(clothes); // 다차원 배열 sort
        for(int i = 0; i < clothes.length - 1; i++){
            if(clothes[i][1].equals(clothes[i+1][1])) sameKindOfClothesCnt++;
            else {
                if(sameKindOfClothesCnt != 1){
                    answer *= sameKindOfClothesCnt + 1;
                    sameKindOfClothesCnt = 1;
                }else{
                    answer *= sameKindOfClothesCnt + 1;
                }
            }
        }
        answer *= sameKindOfClothesCnt + 1; // 마지막 종류의 이름 계산
        return answer - 1;
    }
    public String[][] clothesSort(String[][] clothes){
        Arrays.sort(clothes, (num1, num2) -> {
            return num1[1].compareTo(num2[1]);
		});
        return clothes;
    }
}
```