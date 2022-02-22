---
layout: post
title: analysis-statistics-post2
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - analysis
  - statistics
---

## 통계 : 분산 / 표준편차 / 공분산 / 상관계수

### Variance

평균이나 중앙값은 데이터의 중심을 표현하는데 사용되는 값이라면, 분산과 표준편차는 <strong>데이터가 얼마나 넓게 퍼져있는지<strong>를 나타내는 값

평균과 거리가 먼 점들이 많다면 데이터가 많이 퍼져있다는 것을 알 수 있다.

평균은 각 데이터의 중심이기 때문에, 모든 편차를 다 더하면 0이 되거나, 상쇄될 수 있다.

따라서, 제곱하여 더해준다.

(편차) = (변량) - (평균)

- 편차의 제곱합 / 데이터의 수 = 분산

![image](https://user-images.githubusercontent.com/87109907/155051092-f9cf7caa-ee97-4652-b864-541c6e01e63e.png)


### 표준편차

- 표준편차는 <strong>분산의 양의 제곱근</strong>으로 정의
- 편차를 '제곱'하면서 값이 크게 증가한다.
- 예를들어 시험점수 데이터라고 했을 때,
   - 편차가 3이라면 우리는 3점차이 나는구나 라고 알 수 있다.
   - 이 값을 제곱하면 9가 되는데, 이 숫자가 무엇을 의미하는지 혼란스러울 수 있다.
   - 따라서 분산에 루트를 씌우는 것은 제곱하면서 증가했었던 값을 다시 원래 단위로 맞추는 과정이다.

![image](https://user-images.githubusercontent.com/87109907/155051323-1803bfa8-e836-4872-9a2a-198b2777961d.png)

### 공분산

앞에서는 한 자료의 퍼져 있는 정도 분산에 대해 봤다면 여러 필드 사이의 상관관계를 살펴볼 수 있는 공분산에 대해 알아보자.

- 아래 유전자 x와 y의 그래프를 보자.
- 점들을 보면 두 값이 서로 양의 상관관계가 있어보인다. (x증가시 y도 증가)

![image](https://user-images.githubusercontent.com/87109907/155051468-bc565ac9-cc21-419f-acf6-09743259a662.png)

- x와 y의 관계를 나타내는 선 하나를 그려보자

![image](https://user-images.githubusercontent.com/87109907/155051516-b3843153-8c65-4fcb-bd07-a5f831308e3b.png)

- x가 주어졌을 때 y를 알 수 있다.

![image](https://user-images.githubusercontent.com/87109907/155051556-3f84515a-9a93-4043-a62e-84e17e8dc135.png)

- 데이터가 더 선에 가까울수록, x와 y의 관계는 강하다고 말할 수 있다.

![image](https://user-images.githubusercontent.com/87109907/155051711-72f555f9-0676-4f90-8c97-be7591d4d5fd.png)

- 공분산의 수식

![image](https://user-images.githubusercontent.com/87109907/155051752-f45e0bb3-0696-4ef9-a271-c09df208bee1.png)

- 선형관계가 없으면 다음과 같이 -,+,-,+,,, 공분산이 커지지 않는다.

![image](https://user-images.githubusercontent.com/87109907/155051821-273c5e11-d37d-4028-9078-6a813ed99bd2.png)

### 상관계수

- 공분산은 값의 스케일이 크면 무한히 커질 수 있다.
- <strong>각각ㄱ의 분산으로 공분산을 나눠서 값을 -1 ~ 1 사이의 값으로 들어오도록</strong> 스케일을 조정한 값이 상관계수이다.

![image](https://user-images.githubusercontent.com/87109907/155051936-ecff4287-786a-403f-8bc6-9d25bfb9dd1e.png)

![image](https://user-images.githubusercontent.com/87109907/155051973-1786608f-d2f6-42b3-a78c-6daf4f483ddb.png)

- 단점 : 선형이 아닌 관계는 파악하기 힘들다.

![image](https://user-images.githubusercontent.com/87109907/155052010-0015fdc7-e3bf-411a-b6db-73f919cc2bd5.png)


