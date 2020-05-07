## SQL

Structure Query Language, 관계형 데이터베이스 모델을 위한 데이터베이스 언어



#### DDL SQL (Data Definition Language)

> 데이터베이스 스키마 생성, 스키마 삭제, 스키마 변경 담당



- ##### 테이블 생성 예시

```sql
CREATE TABLE 테이블명 (
   #속성명 | 타입 | 조건,
   id varchar2(15) ,
   pass varchar(15) not null,
   no number(5),
   primary key (id),
   foreign key (pass) references 테이블명
);
```

- ##### 스키마 삭제

```sql
DROP TABLE 테이블명;
```

- ##### 스키마 변경

```sql
#새로운 속성 추가
ALTER TABLE 테이블명 ADD 속성명 타입;

#속성 제거
ALTER TABLE 테이블명 DROP 속성명;
```



<h4>DML SQL (Data Manipulation Language)</h4>

> 데이터베이스의 인스턴스 조작하는 언어, 인스턴스의 생성, 조회, 삭제, 변경



- ##### 기본 형식

```sql
SELECT 속성명
FROM 테이블명
WHERE 조건;
```

- ##### SELECT

> query 결과에서 사용자가 보고 싶은 속성 리스트

```sql
SELECT * // "*"는 모든 속성을 의미한다.
SELECT 속성1, 속성2 // 속성1과 속성2를 가지는 테이블
```

- ##### FROM

> query에 관련된 테이블을 나열

```sql
FROM 테이블1, 테이블2 // 테이블1과 테이블2의 카타시안곱 연산 결과인 테이블이다.
```

- ##### WHERE

> 결과 tuple이 만족해야하는 조건을 명시

```sql
WHERE name = "minsoo" and age > 20
```

<hr>

- ##### Join

> natural join, inner join, left outer join, right outer join, outer join 

1) natural join

```sql
SELECT *
FROM TABLE1 natural join TABLE2
```



2) inner join

```sql
SELECT *
FROM TABLE1 inner join TABLE2 // inner 생략 가능
```



3) left outer  join

```sql
SELECT *
FROM TABLE1 left outer join TABLE2
```



4) right outer join

```sql
SELECT *
FROM TABLE1 natural join TABLE2
```

<hr>

- ##### 재명명

```sql
SELECT 속성명1, 속성명2 속성명3
SELECT 속성명1, 속성명2 as 속성명3
```

> 속성명2를 속성명3으로 재명명

<hr>

- ##### 정렬

```sql
SELECT distinct 속성
FROM 테이블
order by 속성; // order  by 속성 desc
```

> ''속성''에 따라 기본 값으로 오름차순 정렬, desc 사용지 내림차순 정렬

<hr>

- ##### 집합

> 중복을 포함하려면 "union all", "intersect all", "except all" 을 사용해야함

```sql
(SELECT ....) union (SELECT ....)        //합집합 
(SELECT ....) intersect (SELECT ....)    //교집합
(SELECT ....) except (SELECT ....)       //차집합
```

<hr>

- ##### 집계함수

```sql
SELECT count(*)
FROM 테이블1;
```

> 모든 tuple의 값 계산

```sql
SELECT count(distinct 속성1)
FROM 테이블1;
```

> 유일한 값 반환

```sql
SELECT avg(속성1), max(속성1), min(속성1)
FROM 테이블1;
```

> 각각 평균, 최대, 최소 값 반환

```sql
SELECT 속성1, count(*)
FROM 테이블1
GROUP BY 속성1;
```

> 특정 속성 값으로 분류 후 집계함수 적용

```sql
SELECT 속성1, avg(속성2)
FROM 테이블1
GROUP BY 속성1
HAVING avg(속성2) > 2222; //집계 조건
```

> 특정 집계 조건을 만족하는 경우만 집계 

<hr>

- ##### 삭제

> Tuple 단위로 삭제

```sql
DELETE FROM 테이블명
where 속성명="속성";
```

- ##### 삽입

> Tuple 단위로 삽입

```sql
INSERT into 테이블명 values ('a', 'b', 'c');
```

- ##### 갱신

> Tuple 단위로 갱신

```sql
UPDATE 테이블명
set 속성명 = (새로운 속성 조건) ;
```

