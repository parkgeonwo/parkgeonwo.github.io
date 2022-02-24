---
layout: post
title: analysis-analysis-method-post1
description: >

sitemap: false
hide_last_modified: true
categories:
  - analysis
  - analysis-method
---

## 분석 : 유저데이터 분석하기

### 목차

- 실제 회사들은 어떤 데이터를 가지고 있을까?
- 데이터에서 지표를 만들어 내는 방법
- 유저 행동 데이터에서 얼마나 다양한 것들을 알 수 있을까?
- 유저수와 세션수
- 코호트 분석
- 그 외 지표들( 세션의 길이, 이탈률, CLV(LTV) )

### 실제 회사들은 어떤 데이터를 가지고 있을까?

- 회사의 제품/서비스에 대한 데이터
- 고객 데이터
- 서비스와 고객의 <strong>인터렉션으로 발생하는 데이터<strong>

단순히 우리가 가지고 있는 데이터가 제품과 고객 정보 밖에 없다면, 분석할 수 있는 재료가 그렇게 많지 않다.

<strong>제품에 대한 고객의 반응, 서비스 내 유저의 활동으로 인해 유의미한 데이터가 생성</strong>된다. 이를 <strong>로그(기록), 이벤트 정보</strong>라고 말한다.

### 데이터에서 지표를 만들어 내는 방법

- 현상을 요약하는 지표 : 비즈니스에 대한 가설을 세우고 그에 맞는 적절한 지표를 세울 줄 알아야 한다.

- 좋은 지표란 무엇일까 ?

1. 좋은지표는 이해하기 쉽다.
2. 좋은 지표는 상대적이다.
3. 좋은 지표는 비율로 표현된다.
4. 좋은 지표는 문제를 해결할 수 있어야 한다.
5. 정의가 명확해야 한다.

### 유저 행동 데이터에서 얼마나 다양한 것들을 알 수 있을까?

- 우리 서비스의 Active User는 얼마나 되나요 ?
   - active user는 특정 기간안에 어플리케이션이나 웹사이트에 방문하는 unique 유저수를 의미
   - Daily Active Users(DAU) : 하루 동안 방문하는 유니크한 유저수
   - Weekly Active Users(WAU) : 한주 동안 방문하는 유니크한 유저수
   - Monthly Active Users(MAU) : 한달 동안 방문하는 유니크한 유저수

- DAU / MAU = 유저가 자주 방문하는 서비스 인가?
   - DAU / MAU = 3.3%라면 1달 동안 거의 매일 새로운 유저가 유입되는 서비스이다.
   - DAU / MAU = 3.3%라면 어제 유저들이 매일 방문하는 서비스이다.

- Active Users 의 장단점
   - 거의 모든 서비스에서 쉽게 구하는 자주 쓰이는 지표 but 방문만 보기 때문에 서비스 내 활동성 있는 유저 또는 전환한 유저가 얼마나 되는지 측정 불가

### 유저수와 세션수

- 처음 방문해서 사용하다가 서비스에서 나가기까지의 여정을 하나의 세션으로 간주한다.
- 세션의 기준은 회사마다 다르고 분석마다 다르니 제대로 정의해야한다.

- 페이지뷰수 : 화면이 전환되는 것을 기준으로 +1 더한다.

- 질문하기 
   - 유저수 대비 페이지뷰 수가 많다면 ?
   - 유저수 대비 페이지뷰가 적다면 ?
   - 유저수와 세션수가 같다면 ?
   - 유저수 대비 세션수, 페이지뷰수가 많다면 ? 

### 코호트 분석

- 코호트 분석 ?
   - 동일 집단끼리 울타리로 묶고, 다른 집단과 기간 별 행동이나 패턴을 비교하는 것

![image](https://user-images.githubusercontent.com/87109907/153826917-068ad7bd-5262-4e6c-9fb6-e3696b091fbf.png)

![image](https://user-images.githubusercontent.com/87109907/153826966-90c77b1b-c166-43bd-aa56-0cb8250285f8.png)

![image](https://user-images.githubusercontent.com/87109907/153827018-a2e13131-4281-42b6-ab19-d3d329b50b6f.png)

### 그 외 지표들( 세션의 길이, 이탈률, CLV(LTV) )

- 세션의 길이
   - 유저가 방문해서 어느 정도의 시간동안 머무르는지도 중요
   - 들어와서 1초만에 나가면, 의미있는 활동은 아니다.

- 이탈률(Bounce rate)
   - 서비스에 들어와 아무것도 하지 않고 나가는 것도 의미있을까?
   - <strong>이탈(Bounce)</strong> = 서비스에 방문하고 <strong>아무 행동(Event)없이 나가는 경우</strong>를 말한다.

- CLV( Customer Lifetime Value ), LTV( Lifetime Value )
   - <strong> 고객(Customer) + 생애(Lifetime) + 가치(Value) </strong>
   - 고객들이 우리 서비스에 들어와서 나가기까지 얼마나 많은 기여를 하는가?
   - 우리가 고객을 유치하는 데 쓰는 비용이 적합한지 알 수 있다.
   - 고객, 생애, 가치를 어떻게 정의할 것인지 고민해야한다.

![image](https://user-images.githubusercontent.com/87109907/153827815-bcc09c81-22aa-4d8b-8121-5df853e1b01e.png)

![image](https://user-images.githubusercontent.com/87109907/153827885-eeb1abf5-8dbd-466d-b60b-96798228bc3d.png)

