---
layout: post
title: analysis-analysis-method-post2
description: >

sitemap: false
hide_last_modified: true
categories:
  - analysis
  - analysis-method
---

## 분석 : 유저 군집 분석하기

### 목차

- 클러스터링의 개념 
- 클러스터링의 종류
   - Partition-based Clustering
   - Hierarchical based Clustering
   - Density based Clustering
- 실루엣 계수 (Silhouette Coefficient)
- 차원 축소 (Dimension Reduction)

### 클러스터링, 군집화

- 데이터가 주어졌을 때, 여러 개의 그룹으로 나누는 것
- 유사한 특성을 가진 그룹을 발견해내는 일

- <strong>내부 멤버들 간의 사이(intra-cluster)</strong>는 가깝고
   - <strong>그룹간 사이(inter-cluster)</strong>는 멀게 그룹을 만드는 것
- 그룹에 대한 정답이 있으면 분류 문제이지만
   - <strong>클러스터링은 비지도 학습</strong>으로 어느 그룹에 있는지 정답이 없다.

![image](https://user-images.githubusercontent.com/87109907/155440419-ad8c16a9-6404-4d37-a49e-ae7a847848d1.png){: width = "300" height ="300"}

- 사용 사례
   - 유사한 뉴스 그룹으로 묶기 : 문서 군집화
   - 가까운 위치 좌표끼리 묶기
   - 유사한 유저군 나누기 : 마켓 세분화 (시장을 적절한 수로 나누고, 각 시장, 타켓 별로 효과적인 정책을 찾아낸다.)

   - sns 관심사 기반 클러스터링
   - 자율 주행 이미지 인식 클러스터링

### 클러스터링의 종류

클러스터링은 목적과 방법에 따라 매우 다양한 모형이 존재하며, 사용법도 각자 다르고 원하는 목적과 데이터의 형태에 따라 맞춰 사용해야한다.

- Partition-based Clustering
- Hierarchical based Clustering
- Density based Clustering


#### Partition-based Clustering

- 미리 군집(그룹)의 수를 정해두고 클러스터링 하는 방식
- 대표 알고리즘
   - K-means
   - K-Medoids

- K-means clustering

![image](https://user-images.githubusercontent.com/87109907/155440982-9eb80322-f8a6-479f-9f67-6bc39e339234.png){: width = "600" height ="400"}

![image](https://user-images.githubusercontent.com/87109907/155441070-50174abe-2b72-4034-9a1c-3706695d18f6.png){: width = "600" height ="400"}

#### Hierarchical based Clustering

여러개의 군집 중에서 가장 유사도가 높은 혹은
<strong>거리가 가까운 군집 두 개를 선택하여 하나로 합치면서 군집 개수를 줄여가는 방법</strong> agglomerative clustering (합체 군집)라고도 한다.

![image](https://user-images.githubusercontent.com/87109907/155441337-4a7b7ca0-a7fd-44ed-b49f-c11ca06f48a1.png){: width = "600" height ="400"}

가까운 데이터를 서로 묶기 위해서는 먼저 각 군집 간 거리를 계산해야 한다.

- Centroid Distance
   - 각 군집의 중심점 사이의 거리를 계산하는 방법
   - 계층 클러스터링이 아니더라도 사용할 수 있는 방법
- Median Distance
   - Hierarchical based Clustering 에서 사용할 수 있는 방법
   - 군집 u가 군집 s와 군집 t의 결합으로 생성된 군집이라면
      - 중심점을 새로 계산하지 않고, 기존 s와 t의 중심점의 평균을 이용한다.
      - 더 빠르게 계산할 수 있다.


#### Density based Clustering

데이터가 밀집한 정도, 밀도를 이용한 클러스터링 방법이다.

- 군집의 개수를 사용자가 지정할 필요 없다.
- 초기 데이터로부터 근접합 데이터를 찾아나가는 방법으로 군집을 확장

- 필요한 파라미터는 2가지 : "근접하다"를 정의
   - 최소거리 a (다른 점들을 이웃으로 묶기 위한!)
   - 최소 데이터 개수 b(밀집 지역으로 정의하기 위함!)
- 최소 거리 a 안에 있는 데이터는 이웃이다.
- 최소 거리 a 안에 최소 데이터 개수 b 이상의 데이터가 있으면, 이 데이터를 core로 정의
- core 데이터는 하나의 클러스터를 형성, 그 core와 a 거리 내에 있는 점들은 같은 클로서트로 분류

![image](https://user-images.githubusercontent.com/87109907/155446104-3e195f8c-009d-418a-997a-04a35b720c55.png){: width = "600" height ="300"}

k-means는 중심점을 기준으로 그룹을 형성하기 때문에, <strong>원의 형태</strong>로 군집 생성,

서로 이웃한 데이터들을 같은 클러스텡 포함시키기 때문에 <strong>불특정한 모양</strong>의 클러스터가 생성

### 실루엣 계수 (Silhouette Coefficient)

- 모든 데이터 쌍 (i,j) 에 대한 거리나 dissimilarity를 구한다.
   - a_i : i 와 같은 군집에 속한 원소들의 평균 거리
   - b_i : i와 다른 군집 중 가장 가까운 군집까지의 거리

![image](https://user-images.githubusercontent.com/87109907/155446544-9cbb83a8-9ac5-478e-940a-25b11c1bcaad.png){: width = "200" height ="100"}

만약 a 같은 군집 내 평균 거리가 더 가깝다면 양수, 다른 군집과의 거리가 가깝다면 음수

![image](https://user-images.githubusercontent.com/87109907/155446660-403f219f-cc93-479c-9dc3-4584638f3a12.png){: width = "400" height ="300"}


### 차원 축소 (Dimension Reduction)

#### 차원의 저주

- Feature 들이 늘어나면 마냥 좋은게 아니다. 학습에 소요되는 시간과 비용이 UP
- 데이터간 빈 공간들이 많이 생긴다 (컴퓨터에서는 모든 값이 0이 된다.)
- 데이터를 학습하는데 차원이 증가하면서 학습 데이터 수가 차원의 수보다 적어져 성능이 저하되는 현상 --> Feature를 줄여서 성능 저하를 막자

- 복잡도로 인한 모델의 성능 저하를 줄인다.

![image](https://user-images.githubusercontent.com/87109907/155447134-3ee7a8ed-e750-471d-9286-0a2e6d92548b.png){: width = "500" height ="300"}

- 2-3 차원으로 줄이다면 시각화에 효과적이다.

<strong>Feature Seletion</strong>

feature의 중요도나 랭킹을 매겨, feature 의 subset을 추출하거나, 불필요한 feature 제거

<strong>Feature Extraction</strong>

기존 feature를 조합하여 새로운 특징을 생성

### PCA : 차원 축소의 대표적인 방법

- 차원을 낮추고 싶다. 근데 "잘" 낮추고 싶다.
   - 데이터의 feature가 많을수록 데이터는 다양한 representation 표현을 가진다.
   - 다양한 표현 - 데이터 간 거리 - 데이터간 편차를  잘 유지시키는 선을 찾겠다.

![image](https://user-images.githubusercontent.com/87109907/155447578-8365e6a2-16c0-4af8-9218-d44de8fe0e9a.png){: width = "600" height ="300"}

- 그렇기 때문에 우리는 편차의 합 = 분산이 잘 보존되는 선을 찾아서, 그 선에 점들을 투영시킨다.
- 분산, 즉 데이터가 잘 퍼져있는가?

![image](https://user-images.githubusercontent.com/87109907/155447705-2df126d0-7220-466b-93ea-a6cfc13a9632.png){: width = "600" height ="300"}

- 첫번째 선은 구할 수 있다. 분산이 최대화되는 선을 그렸다.
- 두번째 선은 첫번째 선과 직교하는 선을 찾으면 그것이 두번째 선이 된다.

![image](https://user-images.githubusercontent.com/87109907/155447838-55ae282e-c00f-40b3-9228-477a3311eb59.png){: width = "400" height ="400"}

#### PCA 구하는 방법?

첫째, 공분산 행렬

- feature 들의 변동, 즉 얼마만큼이나 함께 변하는가를 행렬로 표현

![image](https://user-images.githubusercontent.com/87109907/155448135-d7efc49c-0126-4fbd-b115-4ad8665c0ee3.png){: width = "300" height ="250"}

둘째, Eigenvector, eigenvalue

- v = eigenvector 고유벡터
- Lambda = eigenvalue 고유값

![image](https://user-images.githubusercontent.com/87109907/155448251-0b826a82-cad9-408d-84d4-142b60e603b6.png){: width = "400" height ="200"}

- A라는 행렬을 곱했는데 방향(각 원소들)은 똑같고, scale(크기)만 달라진다.
- A라는 행렬을 곱했을 때(=v를 선형변환 시켰을 때) 벡터가 얼마나 변하는지를 보여주는 값!

- A: 공분산 행렬 - 데이터의 분산을 표현
- v는 데이터가 어떤 방향으로 분산되어 있는지를 타나낸다.
- Lambda 고유값은 얼마나 그 공간이 퍼지는지(크기)를 말해준다.

![image](https://user-images.githubusercontent.com/87109907/155448556-cb518380-cae3-4ad3-bce1-2666b8922f05.png){: width = "700" height ="400"}






