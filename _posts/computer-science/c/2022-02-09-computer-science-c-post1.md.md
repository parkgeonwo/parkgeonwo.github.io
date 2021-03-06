---
layout: post
title: computer-science-c-post1
description: >

sitemap: false
hide_last_modified: true
categories:
  - computer-science
  - c
---

boost course의 강의 내용으로 공부를 진행하였습니다.

## C 기초

그래픽 인터페이스로 상호작용성이 좋은 스크래치로도 간단한 프로그래밍을 할 수 있지만, 텍스트 기반의 프로그래밍 언어를 이용해도 컴퓨터에게 동일한 일을 하게 할 수 있습니다. 가장 널리 쓰이는 프로그래밍 언어중 하나인 C의 기초를 배워보겠습니다.

### 학습 목표

C로 “hello, world”를 출력하는 프로그램을 만들 수 있습니다.

### 핵심 단어

- stdio.h
- clang
- 컴파일러

### C언어

```
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}

```
C는 아주 오래되고 전통적인 순수 텍스트 기반의 언어입니다.

여러분들 중에서는 C를 이미 공부하신 분들도 있을 수 있고,

처음 접하하는 분들은 이런 이상한 영어들이 적혀있는 것을 보면 두려움이 생기실 수도 있습니다.

하지만 앞으로 있을 강의를 차근차근 듣다보면 위의 모든 코드는 물론이고, 그 이상을 이해하실 수 있을 것입니다.

우선 검은색 바탕에 있는 이상한 글씨들은 아래의 스크래치 블록과 결과적으로 정확히 같습니다.

![1](https://cphinf.pstatic.net/mooc/20200608_293/1591590786465biqfW_PNG/mceclip1.png)

하나하나  설명하자면 int main(void) 는 스크래치의 “초록색 깃발을 클릭했을 때” 블록과 같은 역할을 합니다.

즉 '시작한다'의 의미를 가지고 있다고 보면 됩니다.

앞으로 우리가 작성할 코드 모두는 이 int main(void) { }의 중괄호 사이에 작성하게 될 것 입니다.

![2](https://cphinf.pstatic.net/mooc/20200608_142/1591590807328O5ndC_PNG/mceclip2.png)

C에서는 스크래치에서의 say라는 함수는 없습니다. 대신에 printf라는 함수가 있습니다.

printf(“hello, world\n”) 은 스크래치의 “‘hello, world’라고 말하기” 블록과 같은 역할을 합니다.

글자나 단어, 문장을 적을 때는 언제나 텍스트에 " " 쌍따옴표로 감싸야 합니다.

그리고 우리가 일상에서 문장의 끝에 마침표(.)를 붙이는 것 처럼 C에서는 세미콜론(;)을 붙여야 합니다.

(아래 사진파일에는 나와있지 않지만 \n은 줄바꿈의 기능을 합니다. 키보드에서 ENTER의 기능과 동일합니다.)

위의 여러가지 기능들은 C에서 중요하게 사용되는 기본적인 내용이므로 꼭! 기억해주세요.

![3](https://cphinf.pstatic.net/mooc/20200608_176/1591591032244GQg28_PNG/mceclip3.png)

#include <stdio.h>는 “stdio.h”라는 이름의 파일을 찾아서 “printf” 함수에 접근할 수 있도록 해줍니다.

이게 무슨 말일까? 라고 생각이 드실 거라고 생각이 듭니다.

하지만 이것은 지금 크게 중요하지 않습니다.

오늘 제일 중요한 것은 중간에 있는 printf("hello, world")입니다.


우리가 Word로 문서를 저장했을때 "문서.docx"와 같이 .docx가 붙는 것 처럼,

C로 작성한 코드는 “파일이름.c”로 저장해야 합니다. (확장자 “.c”는 C로 작성된 코드라는 의미입니다.)

마이크로소프트의 Word 처럼 자동적으로 붙여주지 않기 때문에 C의 경우에는 직접 .c를 붙여줘야 합니다.

### 컴파일러


우리가 직접 작성한 코드는 “소스 코드” 라고 불립니다. 이를 2진수로 작성된 “머신 코드”로 변환해야 컴퓨터가 이해할 수 있습니다. 이런 작업을 컴파일러라는 프로그램이 수행해줍니다.

![4](https://cphinf.pstatic.net/mooc/20200608_25/1591593011509xRkDi_PNG/mceclip4.png)

터미널창의 명령어 프롬프트에서 “$” 기호 옆에우리가 원하는 명령어를 입력하면 됩니다.

clang hello.c 라는 명령어는 “clang” 이라는 컴파일러로 “hello.c”라는 코드를 컴파일하라는 의미입니다. 

그 결과 a.out 이라는 파일이 생성됩니다.

./a. out 이라는 명령어를 실행하면 컴퓨터가 현재 디렉토리에 있는 a.out이라는 프로그램을 실행하게 해줍니다.
(./a. out에서 제일 앞에 있는 .은 지금 있는 현재 폴더를 나타냅니다.)

참고) 왜 저는 줄바꿈 할때 \(백슬래시)가 ₩(원화)로 보이는 것이죠?
-> 해당 문제는 '한글 윈도우' 운영체제에서만 생기는 현상입니다.
한글 윈도우에서는 \를 ₩로 표시를 해주기 때문입니다. 따라서 ₩로 표시가 되어도 문제 없습니다.


[Clecture.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8029763/Clecture.pdf)

[Cstudy.pdf](https://github.com/parkgeonwo/parkgeonwo.github.io/files/8029762/Cstudy.pdf)



