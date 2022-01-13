---
layout: post
title: deep-learning-theory-post1
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - deep-learning
  - theory
---

## 성능 평가 지표

### 정밀도(Precision)와 재현율(Recall)

![500x300](https://media.vlpt.us/images/skyepodium/post/5a1e5052-6094-44a7-af28-ff5b37ed0b75/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-04-12%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%2012.57.50.png "Medium example image")


- 정밀도(Precision)

올바르게 탐지한 물체의 수(TP) / 모델이 탐지한 물체의 개수(TP + FP)

"긍정으로 <strong>예측</strong>한 결과중 TP"

- 재현율(Recall)

올바르게 탐지한 물체의 수(TP) / 실제 정답 물체의 수(TP + FN)

"<strong>실제</strong> 긍정 결과중 TP"

예시 1) 강아지가 20마리 존재할 때 모델이 10마리의 강아지를 검출하여 5마리는 정확히 맞힌 경우

  - 정밀도 = 5/10 = 50% , 재현율 = 5/20 = 25%

예시 2) 강아지가 10마리 존재할 때 모델이 20마리의 강아지를 검출하여 7마리는 정확히 맞힌 경우

  - 정밀도 = 7/20 = 35%, 재현율 = 7/10 = 70%

- 만약 모든 영역에 대하여 전부 사물이 존재한다고 판단을 해버리면 어떤 일이 벌어질까 ?

재현율은 높아지지만, 정밀도는 떨어지게 됩니다.

- 만약 매우 확실할 때만(confidence가 높을 때만) 사물이 존재한다고 판단하면 어떤 일이 벌어질까 ?

정밀도는 높아지지만, 재현율을 떨어지게 됩니다.

### Average Precision

- 일반적으로 정밀도와 재현율은 반비례 관계를 가진다.
- 따라서 Average Precision 으로 성능을 평가하는 경우가 많다.

![400x200](https://innerpeace-wu.github.io/images/posts/metric/ap.png "Medium example image")

### IoU (Intersection over Union)

- IoU란 두 바운딩 박스가 겹치는 비율을 의미한다.
  - 성능 평가 예시 : mAP@0.5 는 정답과 예측의 IoU가 50% 이상일 때 정답으로 판정하겠다는 의미
  - NMS 계산 예시 : 같은 클래스(class)끼리 IoU가 50% 이상일 때 낮은 confidence의 box 제거

![400x200](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FwNXOK%2FbtqSpGVHmHc%2FKbsxRBSs6KymYB3PkEny21%2Fimg.png "Medium example image")

### NMS (Non Maximum Suppression)

- 객체 검출(object detection)에서는 하나의 인스턴스에 하나의 bounding box가 적용되어야 합니다.
  - 여러개의 bounding box가 겹쳐 있는 겨웅에 하나로 합치는 방법이 필요합니다.

![500x300](https://naknaklee.github.io/public/images/2021-03-08-NMS-1.png "Medium example image")

IoU가 특정 임계점(threshold) 이상인 중복 box 제거

