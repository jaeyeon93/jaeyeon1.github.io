---
layout: post
title: 2018-8-27 DB정규화(1)
---


데이터베이스 정규화
-

### DB설계 다시보기

![](https://github.com/jaeyeon93/jaeyeon93.github.io/blob/master/images/database/dbNormalization.png?raw=true)


#### 잘 설계된 테이블이란? 다른테이블(엔티티)의 애트리뷰트 값을 읽어오는 것은 외래키의 참조를 통해서만 가능하다.
- people, Department테이블이 존재할때, People에서 Department테이블값을 불러올때, ForeignKey를 통해서만 가지고 와야한다.

#### 잘못된 설계의 문제점
1. 데이터의 중복 발생
2. 이상현상(anormaly)발생 : 삽입이상, 삭제이상, 갱신이상

#### 문제점을 해결하기 위해 정규형을 바탕으로 잘 설계를 해야한다.

#### 정규형 : 이상현상이 잘 안생기는 좋은 테이블이 갖추어야할 조건

- 정규화 : 테이블이 정규형을 만족할 수 있도록 잘 분해하는 과정

### 함수적 종속성(Functional Dependency)
- 두 애트리뷰트 X,Y에서 X가 Y를 함수적으로 결정(X -> Y)
- X의 값이 유일한Y의 값을 결정한다. Y는 X에 함수적으로 종속
- Y가 달라지면 X값은 반드시 달라진다. 반대는 성립안함.
