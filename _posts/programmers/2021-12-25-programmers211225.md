---
title: "programmers [최댓값 구하기]"
excerpt: "programmers [최댓값 구하기]"
categories:
  - Programmers
tags:
  - [Java, algorithm, programmers]
toc: true
toc_sticky: true
date: 2021-12-25
last_modified_at: 2021-12-25
---

![HAN.jpg](/assets/images/programmers.png)

## 문제 설명

ANIMAL_INS 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. ANIMAL_INS 테이블 구조는 다음과 같으며, ANIMAL_ID, ANIMAL_TYPE, DATETIME, INTAKE_CONDITION, NAME, SEX_UPON_INTAKE는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.<br>

|NAME|TYPE|NULLABLE|
|------|---|---|
|ANIMAL_ID|VARCHAR(N)|FALSE|
|ANIMAL_TYPE|VARCHAR(N)|FALSE|
|DATETIME|DATETIME|FALSE|
|INTAKE_CONDITION|VARCHAR(N)|FALSE|
|NAME|VARCHAR(N)|TRUE|
|SEX_UPON_INTAKE|VARCHAR(N)|FALSE|

가장 최근에 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.

<br>

## 입출력 설명

예를 들어 ANIMAL_INS 테이블이 다음과 같다면

|ANIMAL_ID|ANIMAL_TYPE|DATETIME|INTAKE_CONDITION|NAME|SEX_UPON_INTAKE|
|------|---|---|---|---|---|
|A399552|Dog|2013-10-14 15:38:00|Normal|Jack|Neutered Male|
|A379998|Dog|2013-10-23 11:42:00|Normal|Disciple|Intact Male|
|A370852|Dog|2013-11-03 15:04:00|Normal|Katie|Spayed Female|
|A403564|Dog|2013-11-18 17:03:00|Normal|Anna|Spayed Female|

가장 늦게 들어온 동물은 Anna이고, Anna는 2013-11-18 17:03:00에 들어왔습니다. 따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.<br>

시간<br>
2013-11-18 17:03:00<br>
※ 컬럼 이름(위 예제에서는 "시간")은 일치하지 않아도 됩니다.

<br>

```sql
--mysql
SELECT DATETIME
  FROM ANIMAL_INS
 ORDER
    BY DATETIME DESC
 LIMIT 1
;
--oracle
SELECT DATETIME
  FROM (
        SELECT *
          FROM ANIMAL_INS
         ORDER
            BY DATETIME DESC
       )
 WHERE ROWNUM = 1
;
```