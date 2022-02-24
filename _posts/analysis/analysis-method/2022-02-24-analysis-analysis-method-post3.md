---
layout: post
title: analysis-analysis-method-post3
description: >

sitemap: false
hide_last_modified: true
categories:
  - analysis
  - analysis-method
---

## 분석 : 통계적 분석을 이용한 마케팅 데이터 분석 (+ 통계 : 확률, Markov chain)

### 목차

- 도메인 파악하기 : 마케팅
- Markov Chain 이론
   - 확률
   - 조건부 확률


### 회사는 당연히 마케팅을 한다.

고객이 원하는 것을 알아내고 

그것을 회사 서비스/제품과 연결시켜

회사를 성장시킨다.

마케팅 방법은 갈수록 다양해지고 있고, 그중 <strong>디지털 마케팅</strong>비중은 더 커지고 있다.

<strong>데이터로 디지털 마케팅의 효과를 측정</strong>할 수 있을까?

- 디지털 마케팅 ?
   - 특정 목표를 위해 기업 또는 기업의 서비스, 제품, 브랜드 등을 <strong>온라인으로</strong> 고객에게 알리는 행위


![image](https://user-images.githubusercontent.com/87109907/155469059-0e9b58e0-61df-4014-9c31-82717ef8c9ac.png)

우리는 각종 마케팅의 홍수속에서 살아가고 있다.

즉, 하나의 광고만 보고 구매하지는 않는다.

여러 개의 광고에 노출된 후에 구매를 한다.

- 마케팅 용어
   - 광고 채널 (channel)
      - 인스타그램, 카카오톡, 네이버 검색
   - 광고 캠페인 (campaign)
      - 채널안에 여러개의 광고를 만든다. 그 각각을 캠페인이라 한다.
   - 노출(impression)
      - 유저가 켐페인을 한 번이라도 봤다면, 노출되었다고 표현한다.
   - 전환(conversion)
      - 유저가 켐페인을 보고 우리가 원하는 행동을 했다면 "전환"했다고 한다. 보통 구매를 말함


### Markov Chain 이론

#### 확률

- 어떤 일이 일어날 가능성
- 어떤 결과가 나올지 확실하지 않은 상황을 계량
- 실험(experiment) : 주사위를 던진다.
- 표본공간(sample space) : 가능한 주사위의 모든 눈 집합
- 사건(event) : 우리가 관심있는 sample space의 부분집합

P(X="event") = "probability"

여기서 X를 확률변수라고 한다.

어떤 시행에서 표본공간의 각 원소에 단 하나의 실수를 대응시킨 관계를 확률 변수

#### 조건부 확률

- 한 사건이 일어났다는 전제 하에서 다른 사건이 일어날 확률
- B라는 사건이 일어났을 때 A 사건이 일어날 확률 = P(A|B)

![image](https://user-images.githubusercontent.com/87109907/155470061-fee2d7b0-3aff-4fe2-877a-7cf69ecaee7e.png)

- 독립 사건 : P(A) = P(A|B)

#### 날씨 관측 실험으로 보는 Markov Chain

실험 : 날씨 관측

경우의 수 (sample space) : 맑음(0) 또는 흐림(1)

- 첫째날에 맑을 확률
   - P(X1=0)
- 첫째날이 말았을 때, 둘째날도 맑을 확률 ?
   - P(X2=0|X2=0)
- 철째, 둘째, n번째 날도 맑고 n+1 번째도 맑을 확률 ?
   - P(Xn+1=0|X1=0,,,,,,Xn=0)

![image](https://user-images.githubusercontent.com/87109907/155470671-7668758a-f285-45b5-850b-56f59dbc28de.png)

- X1, X2, X3 ... 사건들의 Sequence 가 있을 때
- 다른 state 로 이동하는 확률은 과거 전부가 아닌 현재의 사건에서만 영향을 받는다.

- 이미 과거의 관측값은 더 앞선 과거의 영향을 받은 결과이다.
- 그러므로 직전 관측값만 신경쓰겠다! (memoryless)

![image](https://user-images.githubusercontent.com/87109907/155470933-81778185-4287-48cb-9ea2-acc2370a451a.png)

각각의 경우의 수를 Markov Chain 에서는 <strong>state</strong>라고 한다.

N번째 날이 맑음일 때 N+1 번째 날이 맑음일 확률은 0.7이다.

P(Xn+1=1|Xn=1) = 0.7 (1=맑음 , 0=흐림)

n번째 시점의 확률 변수가 i 일때, n+1 번째 시점에 확률변수가 j가 될 조건부 확률을 <strong>전이확률(Transition Probability)</strong>라고 한다.

#### 전이확률 행렬

![image](https://user-images.githubusercontent.com/87109907/155471317-2b6c13ae-9f3d-4dae-b6ab-658d60b862c1.png)

행(row)에는 현재 상태를, 열(column)에는 다음 상태를 표시하여 확률을 배열한 행열

#### 각 채널의 전환에 대한 기여도는 어떻게 계산 가능할까? (마케팅 도메인으로 확장)

![image](https://user-images.githubusercontent.com/87109907/155471549-f1fa24c7-e9a2-436e-b1e4-becd310347de.png)

- 앞의 그림에서 카카오의 전환에 대한 기여도는
   - 카카오가 전환에 암것도 기여하지 못해서 제거된 상황을 가정하여 계산
   - 기존 total conversion이 20% 였는데
   - 카카오는 100% 전환 실패한다고 가정했을 때 얼마나 전환율이 떨어질까 ?
   - 이를 <strong>Removal Effect</strong> 제거 효과라 한다.

![image](https://user-images.githubusercontent.com/87109907/155471810-3be77217-af06-42bf-8526-6f377b7e9ff1.png)

#### Absorbing Markov Chain

Absorbing state(흡수되는 마코브 체인)

끝이 정해져 있는 마코브 체인, 이리저리 이동하다 결국 이동을 끝맺을 수 있다.

![image](https://user-images.githubusercontent.com/87109907/155472071-c79a0eff-0232-48a1-ad13-29dc7bacb002.png)

행렬로 표현

![image](https://user-images.githubusercontent.com/87109907/155472111-6cf5239c-6091-4be8-ab59-7cb7db885538.png)

- Absorbing Markov Chain 공식

![image](https://user-images.githubusercontent.com/87109907/155472181-4603b337-009e-444a-b459-fea6d3e615d4.png)

예시에 대입하면

![image](https://user-images.githubusercontent.com/87109907/155472274-0b3c9bdd-3cbd-48f8-8cde-fd487955cb24.png)

Absorbing Markov Chain 은 반복되면 결국 다음 행렬로 수렴한다.

P_bar 의 (i,j)는 계속해서 transition 을 반복하다 처음 i 에서 최종 j가 되어 더이상 변화하지 않을 확률을 나타낸다.

![image](https://user-images.githubusercontent.com/87109907/155472344-892b502c-8c73-4158-b0b3-1dff424df8c8.png)


앞의 술취한 사람이 최종적으로 집으로 들어갈 확률은,,

![image](https://user-images.githubusercontent.com/87109907/155472743-01bd42a3-df5c-4566-98a8-9093d44560ed.png)


![image](https://user-images.githubusercontent.com/87109907/155472808-21491517-8fb7-4c6a-bdce-4c267ac39429.png)

- 우리가 가진 데이터도 결국 전환/비전환 상태로 끝맺는다.



