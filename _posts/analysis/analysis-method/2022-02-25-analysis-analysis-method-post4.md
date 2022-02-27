---
layout: post
title: analysis-analysis-method-post4
description: >

sitemap: false
hide_last_modified: true
categories:
  - analysis
  - analysis-method
---

## 분석 : 머신러닝을 활용한 마케팅 예산 분배 최적화

### 목차

- 회귀 분석
  - 선형 회귀 (Linear Regression)
  - 로지스틱 회귀(Logistic Regression)

-

### 선형 회귀 (Linear Regression)

머신러닝의 가장 큰 목적
  - 실제 데이터를 바탕으로 모델을 생성해서
  - 다른 입력 값을 넣었을 때 발생할 아웃풋을 예측

이때 우리가 찾아낼 수 있는 가장 직관적이고 간단한 모델은 <strong>선(Line)</strong>이다. 그래서 데이터를 놓고 그걸 가장 잘 설명할 수 있는 선을 찾는 방법을 <strong>선형 회귀(Linear Regression)</strong> 분석이라 부른다.

![image](https://user-images.githubusercontent.com/87109907/155886908-0a248c2c-3285-4a32-bfc8-2c8d5a8baa43.png)

Y = Wx + b

- x와 Y는 이미 알고 있는 값
- W, b는 예측해야 하는 값

#### 회귀 분석의 활용

독립변수(X들)과 종속변수(Y)의 관계를 수치적으로 명확하게 설명하고 싶을 때

X와 Y의 관계를 선형으로 나타낼 수 있을 때

### 로지스틱 회귀(Logistic Regression)

예측하고 싶다. 무엇을 ?

어떤 범주에 속할 확률을 0에서 1 사이의 값으로 예측 

#### 선형 회귀는 이진 분류를 하지 못한다.

![image](https://user-images.githubusercontent.com/87109907/155887020-e0b01940-de52-454f-84d4-02c186fa51e1.png)


- 선형 회귀
  - Y = Wx + b

- 로지스틱 회귀
  - P(Y=1) = Wx + b

로지스틱 회귀식을 (0,1) 사이의 범위로 떨어지도록 식을 변형해준다. 어떻게 ?

#### sigmoid function을 이용한다.

![image](https://user-images.githubusercontent.com/87109907/155887069-c864678a-d7aa-4be7-8439-73423c2e7fb1.png)

선형식은 간단히 sigmoid 함수를 통해서 (0,1)을 예측하는 선으로 바꿀 수 있다.

![image](https://user-images.githubusercontent.com/87109907/155887199-4557f4f5-5398-4aad-bedb-a72e79c50cf5.png)

Y = Sigmoid(Wx+b)

- 로지스틱 회귀 분석의 활용
  - 예측하려고 하는 값이 이분형(1 또는 0) 일 때 사용한다.
  - 고객 신용도 평가 (우량 / 불량 예측)
  - 질병 예측 (질병 발생 확률 예측)

- 우리가 살펴본 데이터에는 어떤 모델을 사용할까?
- 목적
  - 우리가 산정한 마케팅 예산을 각 켐페인에 분배하고 싶다.
  - 각 캠페인의 유저 전환에 대한 상대적은 기여도를 알고 싶다.
  - 켐페인의 종류는 현재 50개이다.
  - 유저가 본 켐페인들과 해당 켐페인의 카테고리 등 모든 피쳐들을 모아서 <strong>전환을 예측하는 모델</strong>을 만든다. <strong>전환(Conversion) 은 0 또는 1이다</strong> = Logistic Regression 

![image](https://user-images.githubusercontent.com/87109907/155887344-2e3d987f-44f3-4c55-bb2d-6fb13c360eca.png)

- 어떤 켐페인이 전환에 영향을 많이 미쳤을까?
  - 여기서 X는 유저가 본 켐페인들, W는 각 켐페인이 Y에 미친 영향으로 이해

- 모델이 학습된 후 각 켐페인이 전환에 얼마나 기여했는지 <strong>모델이 예측한 파라미터 W</strong>를 가져오려고 한다.



