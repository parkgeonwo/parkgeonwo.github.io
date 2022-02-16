---
layout: post
title: project-post3
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - project
---

## AI-Face-detect-squid-game

AI로 내 얼굴을 분석하여 드라마 오징어게임에서 어떤 출연자와 비슷한지 알려주는 서비스.

학습용으로 만들었습니다. 모바일 전용입니다.

https://parkgeonwo.github.io/AI-Face-detect-squid-game/

<img width="30%" src="https://user-images.githubusercontent.com/87109907/143675994-1562d785-b3cc-4931-b4a6-4528cb9b6728.jpg"/>        <img width="30%" src="https://user-images.githubusercontent.com/87109907/143675997-ee9b2e70-d5b7-46d9-af79-50bfa023ac52.jpg"/>




### 개발 목표

Teachable machine을 통해 11명의 배우들의 사진을 딥러닝 학습하여 딥러닝 모델을 생성하고

딥러닝 모델이 적용된 웹사이트에 사진을 업로드하면 닮은 배우를 알려주는 서비스 개발


### 사용 기술

- HTML
- CSS
- Bootstrap
- Teachable machine(tensor flow)
- Javascript
- Jquery
- Codepen
- Python (크롤링 및 흑백사진으로 변경)


### Advanced Feature

- 파이썬을 활용해 웹크롤링한 사진들을 흑백사진으로 변경

<img width="40%" src="https://user-images.githubusercontent.com/87109907/144372777-3c2cafcf-4655-4597-9e02-2f30a6d76e9a.png"/> <img width="40%" src="https://user-images.githubusercontent.com/87109907/144372853-0fdcce46-73ac-427e-94cd-f021024d2fc7.png"/>

<img width="30%" src="https://user-images.githubusercontent.com/87109907/144373227-640dd65b-d1e0-4235-8c05-a20ced8b0e4d.png"/>

- Teachable machine 학습

<img width="50%" src="https://user-images.githubusercontent.com/87109907/144372281-e6d55a2f-39ef-41dd-906f-092deaf43b38.png"/>


- 기존의 teachable machine 모델은 web cam으로 사물을 판별하는데, 이를 사진 업로드 방식으로 변경 (javascript, jquery, codepen)

<img width="30%" src="https://user-images.githubusercontent.com/87109907/144372015-31583f9f-67d6-4ffa-9f7b-7b2536723812.png"/>
<img width="40%" src="https://user-images.githubusercontent.com/87109907/144371799-a64501f3-a542-4336-a9ce-24360bf27bd4.png"/>
<img width="40%" src="https://user-images.githubusercontent.com/87109907/144371845-97c28756-8364-4918-8ee8-df1ce0cc1368.png"/>




### 개선사항

- 모바일 크기로 코드를 작성했기 때문에 웹에서 사용성이 떨어짐
- 딥러닝 학습시에 적은 수의 사진으로 학습한 결과 정확도가 다소 떨어지는 경향이 있음
- 직접 학습시킨 모델로 적용하는 방법을 공부해야 할것.



