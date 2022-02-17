---
layout: post
title: project-post4
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - project
---

## 전자제품 쇼핑몰 서비스 건강성 분석

[이론 배경](https://parkgeonwo.github.io/analysis/analysis-method/2022-02-14-analysis-analysis-method-post1/)

[통계](https://parkgeonwo.github.io/analysis/statistics/2022-02-14-analysis-statistics-post1/)

[전체 코드](https://github.com/parkgeonwo/user_data_service_analysis)

### 목적 

회사에 들어오는 유저들의 행동 패턴을 파악하고, 서비스가 성장하고 있는지 분석을 목적

### 데이터 설명

- [데이터셋 출처](https://www.kaggle.com/mkechinov/ecommerce-events-history-in-electronics-store/version/1) https://www.kaggle.com/mkechinov/ecommerce-events-history-in-electronics-store/version/1
- 전자 제품 회사의 이커머스 이벤트 히스토리 (캐글)
- 2019년 10월부터 2020년 2월까지 5월까지의 큰 전자제품 온라인 상점의 5달 동안의 유저 행동 데이터를 포함하고 있다
- 각 데이터의 행은 이벤트를 나타내며, 이벤트는 상품과 유저와 관련이 있습니다
- 각 이벤트는 상품과 유저의 many-to-many relation 와 같습니다
- 하나의 세션에는 여러개의 구매 기록이 남을 수 있지만, 1개의 주문으로 봐도 좋습니다 

### 데이터 특이사항

- 정확히 방문만 한 유저는 알 수 없음
   - 여기서는 유저의 방문을 "아래 4개 중 하나의 행동을 해당 날짜에 했음"으로 정의
- 아이템을 조회, 장바구니 담기, 장바구니에서 제거, 구매

### 일자별 유저수는 어떻게 나타날까 ?

![image](https://user-images.githubusercontent.com/87109907/154280147-0c570912-4e9b-4dc9-a0aa-417eff4bf6e0.png)

- 11월 12- 19일 기준으로 peak 를 찍었다가 점차 감소하는 추세
- 유저수가 정체되고 있거나 소폭 감소하는 경향이 있었음

- 주별/월별 유저수 변화
   - 일자별 유저수와 비슷하게 나타났다.

![image](https://user-images.githubusercontent.com/87109907/154281114-e6e4bfae-14d8-4d4a-beb2-5480a316a1ba.png)

- 월별 유저수 변화

![image](https://user-images.githubusercontent.com/87109907/154281397-b66c30ff-043b-40e6-af31-a48c07a3b1d9.png)

### 1달 동안 한 유저는 얼마나 자주 방문하는가? 

- DAU 와 MAU를 비교했을 때, DAU / MAU = 3.6 %
   - 매일 방문하는 유저가 거의 신규 유저고, 1달 동안 다시 방문하는 케이스가 극히 드물었다. (안 좋은 신호일 수 있다.)


### 유저의 서비스 내 활동량은 얼마나 될까?

![image](https://user-images.githubusercontent.com/87109907/154281521-41ec7848-faab-44c3-8b18-03fa5a8e0575.png)

- 유저들은 하루에 거의 1번 방문함 (1.0 - 1.2 세션수)
- 방문 대비 이벤트 수를 보았을 때, 유저의 방문 시 이벤트 수는 소폭 증가하는 경향이 있었다 (1.6 → 1.8)

### 유저들은 다시 방문/구매하고 있는가?

![image](https://user-images.githubusercontent.com/87109907/154281632-166054ac-d818-48f6-8207-8569829b6efd.png)

- 유저들이 처음 방문한 후에 <strong>재방문하는 비율</strong>이 
   - 1개월이 지났을 때는 2%
   - 2개월이 지나면 1% 미만
   - 3개월째 되면 0.5%
   - 0.34%

![image](https://user-images.githubusercontent.com/87109907/154281863-8c5b239f-efd2-40e1-83a3-49d661f691d1.png)

- 유저들이 처음 구매한 후에 <strong>재구매하는 비율</strong>이 
   - 1개월이 지났을 때는 2% 정도
   - 2개월이 지나면 0.6%
   - 3개월째 되면 0.16%


### 결론

- 유저의 재방문 및 재구매가 많지 않고, 들어왔을 때 활동성이 높지 않음
   - 먼저 <strong>신규 방문 유저</strong>를 놓치지 않도록, 재방문을 높일 마케팅이나 가입 유저에 대한 할인 혜택 등 
   - 1번이라도 방문한 유저가 다시 방문하기 위한 혜택 등이 필요함





