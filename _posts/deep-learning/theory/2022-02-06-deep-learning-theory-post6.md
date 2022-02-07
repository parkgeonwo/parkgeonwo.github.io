---
layout: post
title: deep-learning-theory-post6
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - deep-learning
  - theory
---

## 내가 다시 보려고 만든 "밑바닥 부터 시작하는 딥러닝" 정리 4

책 "밑바닥부터 시작하는 딥러닝 1권" 내용 중 다시 보려고 만든 자료입니다. (챕터 6)

### chapter 6

- 이번 장에서 다룰 주제는 가중치 매개변수의 최적값을 탐색하는 최적화 방법, 가중치 매개변수 초깃값, 하이퍼파라미터 설정 방법 등 신경망 학습에서 중요한 주제이다. 오버피팅의 대응책인 가중치 감소와 드롭아웃등의 정규화 방법도 설명하고 배치 정규화도 짧게 알아본다.

### chapter 6.1 매개변수 갱신

- 신경망 학습의 목적은 손실 함수의 값을 가능한 한 낮추는 매개변수를 찾는 것이었다. 이는 곧 매개변수의 최적값을 찾는 문제이며, 이러한 문제를 푸는 것을 <strong>최적화</strong>라고 한다.

### chapter 6.1.2 확률적 경사 하강법(SGD)

- SGD의 수식
   ![100x100](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FFs4Y3%2FbtqFt6ndQjT%2F4QCJLDwHBIgAdwYbeoac01%2Fimg.png)

### chapter 6.1.3 SGD의 단점

- SGD에 의한 최적화 갱신 경로 : 최솟값인 (0,0)까지 지그재그로 이동하니 비효율적이다.
   ![100x100](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc87nGX%2FbtqFtKdIfso%2Fapokj19hld4v1EKY4rydD1%2Fimg.png)

- SGD의 단점은 비등방성 함수(방향에 따라 성질, 즉 여기에서는 기울기가 달라지는 함수)에서는 탐색 경로가 비효율적이라는 것이다.

### chapter 6.1.4 모멘텀

- 모멘텀은 운동량을 뜻하는 단어다.
   ![150x100](https://mblogthumb-phinf.pstatic.net/MjAxODAyMDFfMTMz/MDAxNTE3NDEyNDkzOTY3.xc165v0N5R1xe5ajJO9g5z2sB-CQy3RwT1dfLIg9B3Eg.l09OGIx4-QRW6LjjiaSz7I30NQUfXVzHkEqgFZn0W1og.PNG.worb1605/image.png?type=w800)

   - W는 갱신할 가중치 매개변수, dL/dW 는 W에 대한 손실 함수의 기울기, η는 학습률이다. v 라는 변수가 새로 나오는데, 이는 물리에서 말하는 속도에 해당한다. 위의 식은 기울기 방향으로 힘을 받아 물체가 가속된다는 물리 법칙을 나타낸다.
   - αv항은 물체가 아무런 힘을 받지 않을 때 서서히 하강시키는 역할을 한다. 물리에서의 지면 마찰이나 공기 저항에 해당한다.

   - 모멘텀에 의한 최적화 갱신 경로
   ![200x200](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpWahY%2FbtqJ1KMBFiI%2FSJ8P6njpgqqy7FXH2qKKjk%2Fimg.png)
   - 지그재그 정도가 덜한 것을 알 수 있다. 이는 x축의 힘은 아주 작지만 방향은 변하지 않아서 한 방향으로 일정하게 가속하기 때문이다. 거꾸로 y축의 힘은 크지만 위아래로 번갈아 받아서 상충하여 y축 방향의 속도는 안정적이지 않다. 전체적으로는 SGD 보다 x축 방향으로 빠르게 다가가 지그재그 움직임이 줄어든다.

### chapter 6.1.5 AdaGrad

- 학습률을 정하는 효과적 기술로 <strong>학습률 감소</strong>이 있다. AdaGrad는 개별 매개변수에 적응적으로 학습률을 조정하면서 학습을 진행한다. AdaGrad 갱신 방법의 수식은 다음과 같다.
   - ![200x100](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FH8MY9%2FbtqJ0owhSUL%2Fj7keQZ0PVQfy7RMS9F9tyK%2Fimg.png)
  
   - 매개변수를 갱신할 때 1/((h)^1/2)을 곱해 학습률을 조정한다. 매개변수의 원소 중에서 많이 움직인(크게 갱신된) 원소는 학습률이 낮아진다는 뜻인데, 다시 말해 학습률 감소가 매개변수의 원소마다 다르게 적용됨을 뜻한다.

   - AdaGrad에 의한 최적화 갱신 경로
   ![200x200](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcHAg5e%2FbtqJWTcMctz%2F6foaiv3ZaaD7mrJ8ZvaRe0%2Fimg.png)

- RMSProp
   - AdaGrad는 과거의 기울기를 제곱하여 계속 더해간다. 그래서 학습을 진행할수록 갱신 강도가 약해진다. 실제로 무한히 계속 학습한다면 어느 순간 갱신량이 0이 되어 전혀 갱신되지 않게된다. 이 문제를 개선한 기법으로 RMSProp라는 방법이 있다. 과거의 모든 기울기를 균일하게 더하는 것이 아니라, 먼 과거의 기울기는 서서히 잊고 새로운 기울기 정보를 크게 반영한다. 이를 지수이동평균이라 하여, 과거 기울기의 반영 규모를 기하급수적으로 감소시킨다.

### chapter 6.1.6 Adam

- 모멘텀과 AdaGrad 두 기법을 융한한 기법 : Adam
- 두 기법의 이점을 조합하여 매개변수 공간을 효율적으로 탐색해준다. 또한, 하이퍼파라미터의 '편향 보정'이 진행된다는 점도 Adam의 특징이다.
- Adam에 의한 최적화 갱신 경로
   ![200x200](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fdt8EvM%2FbtqJWrm9RLv%2FkqUDwalmGKKWswlZ8waVoK%2Fimg.png)


