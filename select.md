# 프로그래머스

# <SQL 고득점 kit>

## SELECT

1. 모든 레코드 조회 하기

```sql
SELECT * FROM ANIMAL_INS    #모든 컬럼 추출시 * FROM 뒤에는 테이블명
ORDER BY ANIMAL_ID;         #정렬할 컬럼 설정
```

2.  역순 정렬하기

```sql
SELECT NAME,DATETIME FROM ANIMAL_INS  
ORDER BY ANIMAL_ID DESC;     #역순으로 정렬 시 DESC 사용
```

3.  아픈 동물 찾기

```sql
SELECT ANIMAL_ID, NAME FROM ANIMAL_INS 
WHERE INTAKE_CONDITION = 'Sick' ORDER BY ANIMAL_ID; #조건 설정 시 WHERE 사용
```

4.  어린 동물 찾기

```sql
SELECT ANIMAL_ID, NAME FROM ANIMAL_INS
WHERE INTAKE_CONDITION != 'Aged'        # != 조건이 아닌 것을 추출
ORDER BY ANIMAL_ID;
```

5.   동물의 아이디와 이름

```sql
SELECT ANIMAL_ID,NAME FROM ANIMAL_INS
ORDER BY ANIMAL_ID;
```

6.  여러 기준으로 정렬하기

- 이름을 사전 순으로 정렬하면 다음과 같으며, 'Jewel', 'Raven', 'Sugar'
- 'Raven'이라는 이름을 가진 개와 고양이가 있으므로, 이 중에서는 보호를 나중에 시작한 고양이를 먼저 조회합니다.

```sql
SELECT ANIMAL_ID,NAME,DATETIME FROM ANIMAL_INS 
ORDER BY NAME, DATETIME DESC;    #DATETIME은 역순으로 정렬
```

7.  상위 N개 레코드

- 동물 보호소에 가장 먼저 들어온 동물의 이름을 조회하는 SQL 문을 작성

```sql
SELECT NAME
FROM (SELECT * FROM ANIMAL_INS 
ORDER BY DATETIME)     
WHERE ROWNUM = 1;   #한 행만 출력
```