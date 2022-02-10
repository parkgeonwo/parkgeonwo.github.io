---
layout: post
title: tableau-post1
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - tableau
---

## ch1. 태블로 이해하기

### Ep.1 디지털로 전환

### 학습 목표

- 불확실성이 높은 현 시점에 기업과 각 구성원들의 당면과제를 살펴봅니다. 

### 핵심 키워드

- 디지털 트랜스포메이션 (Digtial Transformation)

- 데이터 리터러시 (Data Literacy)

- 데이터 시각화 Data Visualization

요즘 기업에서 가장 큰 화두는 Digital Transformation입니다.
Digital Transformation이란 디지털로 변신(변혁)을 한다는 뜻입니다.
예전에는 전통적인 회사들이 제조업, 금융업, 융통업처럼 하나의 분야에서 성장하는 방식이었다면
이제는 모든 산업 분야 및 회사들은 IT를 기반으로 변화하고 있습니다.

기업과 구성원들의 당면 과제인 디지털 트랜스포메이션과 데이터 리터러시에 대해서 살펴봅니다.

[Tableau 활용한 데이터 시각적분석_Ep.1_디지털로 전환.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8038013/Tableau._Ep.1_.pdf)



### Ep.2 태블로 이해 및 설치하기

### 학습 목표

- 태블로의 현재 및 장점을 알아보고 앞으로 발전하는 방향을 알아봅니다. 그리고 태블로 퍼블릭을 설치하고 실습할 준비를 마칩니다.

### 핵심 키워드

- 태블로 (Tableau)

- BI (Business Intelligence)

- 끌어다 놓기 (Drag & Drop)

- 태블로 퍼블릭 (Tableau Public)

태블로 퍼블릭 설치하기 https://public.tableau.com/ko-kr/s/download

태블로 데스크탑 설치하기 (2주 무료 체험) https://bit.ly/TabDown

태블로는 스스로 데이터를 보고 이해하는 셀프 서비스의 분석 영역에서

조직과 조직 구성원이 데이터를 활용하는데 도움을 줍니다.
현재 태블로는 데이터 분석 분야의 신뢰받는 리더*로서
사람과 조직이 한층 더 데이터 기반의 의사 결정을 할 수 있도록 지원합니다.
(*2021년 기준 9년 연속 Gartner가 선정한 Data Visualization and Business Intelligence 분야의 Leader)


여기에서는 Tableau Public을 설치 후 실습을 진행합니다.

[Tableau 활용한 데이터 시각적분석_Ep.2_태블로 이해 및 설치하기.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8038014/Tableau._Ep.2_.pdf)


### Ep.3 태블로 기본 컨셉 이해하기 (1)

### 학습 목표

- 태블로의 기본 컨셉인 측정값과 차원을 알아보고 가장 기본적인 비주얼리제이션인 막대 차트를 만들어봅니다. 

### 핵심 키워드

- 측정값 (Measures)

- 차원 (Dimensions)

- 막대 차트 (Bar chart)

태블로의 가장 기본 컨셉 중 하나는 측정값과 차원입니다. 

측정값은 기본적으로 숫자형식이고 집계를 통해 한 덩어리가 만들어지며,

차원은 그 한 덩어리를 세부적으로 나누어서 보는 기준이 됩니다. 

또한 태블로에서 가장 기본적인 비주얼리제이션은 막대 차트입니다.

태블로에서는 측정값에 있는 데이터 원본 필드 중
초록색 연속형 필드(지리적 역할인 위도, 경도는 제외)를 더블 클릭하면
기본적으로 막대 차트가 만들어집니다.

기본적으로는 집계 방식을 통해 우선 차트를 만들고
이것을 분할해서 보는 기준은 차원의 값으로 결정되는데,
그 출발은 막대 차트부터 시작하게 됩니다.

[Tableau 활용한 데이터 시각적분석_Ep.3_태블로 기본 컨셉 이해하기.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8038015/Tableau._Ep.3_.pdf)


### Ep.4 태블로 기본 컨셉 이해하기 (2)

### 학습 목표

- 태블로의 기본 컨셉인 연속형과 불연속형에 대해 알아보고 가장 기본적인 비주얼리제이션 중 하나인 라인 차트를 만들어봅니다. 

### 핵심 키워드

- 연속형 (Continuous)

- 불연속형 (Discrete)

- 라인 차트 (Line chart)

- 평균 라인 (Average line)

태블로에서는 데이터 원본의 열(Column)에서 만들어진 필드를  불연속형(파란색)인지, 아니면 연속형(녹색)인지에 따라 뷰에서 다르게 표시하게 됩니다.

예를 들어서 연속형은 무한대로 끊어지지 않고 이어지는 성격이라면, 불연속형은 값은 유한하며 개별적으로 구분되는 속성이 있습니다.

- 불연속형은?

파란색 필드 = 불연속형 = 개별적으로 구분

유한한 범위, 뷰에 추가하면 머리글을 추가함

Discrete = Blue, Separate and distinct, finite

Discrete fields draw headers.

- 연속형은?

초록색 필드 =연속형 = 단절이 없고 끊어지지 않는
무한대 범위, 뷰에 추가하면 축을 추가합니다.

Continuous = Green, unbroken, without interruption, infinite

Continuous fields draw axes.

라인 차트는 처음부터 해당 영역까지 기본적으로 연결하는 속성이 강합니다.

따라서 시간 베이스의 추세를 살펴보는데 적합합니다.

라인 차트에도 불연속형과 연속형이 있으며, 각각 적용되는 함수도 다르고 뷰에서 표현하는 방식도 다릅니다.

라인 차트는 전반적인 추세를 보는 경향이 강한 차트이며,

불연속형은 DATEPART 함수를, 연속형은 DATETRUNC 함수가 적용됩니다.

[Tableau 활용한 데이터 시각적분석_Ep.4_태블로 기본 컨셉 이해하기.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8038018/Tableau._Ep.4_.pdf)









