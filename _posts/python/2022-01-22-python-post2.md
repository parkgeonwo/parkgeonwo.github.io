---
layout: post
title: python-post2
description: >
  
sitemap: false
hide_last_modified: true
categories:
  - python
---

## 프로세스와 쓰레드

### 프로세스와 스레드

운영체제에서 어떤 실행 프로그램이 실행된다는 것은 CPU, 메모리, SSD와 같은 컴퓨터 자원을 사용합니다. 따라서 운영체체제는 프로그램들이 마음껏 실행될 수 있도록 전용 '놀이터'와 같은 공간을 제공해주는데 이를 프로세스라고 합니다.

응용 프로그램의 코드는 이 놀이터에서 마음껏 놀 수 (실행 할 수) 있으며 외부 세계에 대해서 걱정할 필요가 없습니다. 하지만 만약 어떤 코드가 자신에게 부여 받은 놀이터 공간를 벗어나 다른 영역으로 가려면 하면 운영체제에 의해 종료되어버립니다.

놀이터에는 응응 프로그램이 놀 수 있습니다. 운영체제 입장에서 놀이터에 있는 플레이어를 스레드라고 부릅니다. 어떤 응용 프로그램은 한 번에 여러 가지 작업을 수행해야 하는 경우도 있습니다. 이 경우 동일한 놀이터(프로세스)에 두 아이(스레드)가 있는데 놀이터에 있는 모든 장난감(컴퓨터 자원)은 공유한다고 생각하면 됩니다.

![400x200](https://postfiles.pstatic.net/MjAyMjAxMjJfMzMg/MDAxNjQyODYxMTAxMDI0.yeUZJPIZ1P_lQt8TzXfVHEefSYfcyQUl9BpcNDeTtcIg.zRN8rhwg_LPjm20YV9LsNyI7J5tGMm600_2GIVQVPL8g.PNG.parkkeonwo/image.png?type=w966)


### 스레드란 ?

여러분이 사용하는 PC에는 윈도우, macOS, 리눅스와 같은 운영체제가 설치되어 있습니다. 운영체제는 컴퓨터를 전체적으로 관리하는 매니저 역할을 합니다. 우리가 프로그램이라고 부르는 것들은 운영체제 위에서 동작합니다. 프로그램이 메모리에 올라가서 실행 중인 것을 프로세스(process)라고 부릅니다. 프로세스의 실행 단위를 스레드라고 합니다. 프로세스는 최소 하나 이상의 스레드를 갖으며 경우에 따라 여러 스레드를 가질 수도 있습니다.

여러분이 윈도우를 사용할 때를 생각해봅시다. 메신저도 사용하고 게임도 하고 문서작성도하고 인터넷도 사용할 것니다. 윈도우는 동시에 실행되는 여러 프로그램들을 잘 관리해야하는데 이런 작업을 스케줄링이라고 합니다. 운영체제는 스케쥴의 단위로 앞서 설명한 스레드를 사용합니다. 여러분이 프로그램을 작성할 때 여러 개의 스레드를 사용할 수 있는데 이를 멀티스레드라고 부릅니다. 이처럼 프로그램을 작성할 때 멀티스레드 형태로 구현을 하면 운영체제에 의해서 동시에 스케줄링(동시처럼 느껴지는) 될 수 있기 때문에 보통 성능이 더 좋아집니다.

![300x300](https://postfiles.pstatic.net/MjAyMjAxMjJfMTIz/MDAxNjQyODYxMTE1NDE4.hNvvU8f7VSB9K52gNT7byZKf2_GT3W_rNLLwnsl077Mg.A_GCRRAfgbo6X8caar-iy9e-lKIpfSF6MvhoV-HIH3Eg.PNG.parkkeonwo/image.png?type=w966)

![400x200](https://blogfiles.pstatic.net/MjAyMjAxMjJfMzMg/MDAxNjQyODYxMTAxMDI0.yeUZJPIZ1P_lQt8TzXfVHEefSYfcyQUl9BpcNDeTtcIg.zRN8rhwg_LPjm20YV9LsNyI7J5tGMm600_2GIVQVPL8g.PNG.parkkeonwo/image.png)

### 파이썬 멀티 쓰레드(thread)와 멀티 프로세스(process)

파이썬은 인터프리터 언어로서 기본적으로 싱글 쓰레드에서 순차적으로 동작한다. 따라서 병렬처리를 하기 위해서는 별도의 모듈을 사용하여 구현해야 한다. 이 글에서는 threding 모듈을 이용한 쓰레드 구현과 multiprocessing 모듈을 이용한 프로세스 구현을 소개한다.

- threding 모듈로 멀티쓰레드 구현하기

파이썬에서 멀티 쓰레드를 구현하는 방법은 threding 모듈(High level)을 사용하거나 thread(Low level) 모듈을 사용하는 것이며, 현재 thread 모듈은 deprecated 되어 threading 모듈을 사용하는 것을 권장한다.

먼저 0부터 100,000,000 까지의 합을 구하는 계산 프로그램을 하나의 쓰레드로 동작하게 만들어보자.

```
from threading import Thread

def work(id, start, end, result):
    total = 0
    for i in range(start, end):
        total += i
    result.append(total)
    return

if __name__ == "__main__":
    START, END = 0, 100000000
    result = list()
    th1 = Thread(target=work, args=(1, START, END, result))
    
    th1.start()
    th1.join()

print(f"Result: {sum(result)}")
```

쓰레드는 threading 모듈의 Thread 함수로 쓰레드 객체를 받아 사용한다. target은 쓰레드가 실행할 함수, args는 그 함수의 인자들을 의미한다. start 함수로 쓰레드를 시작하고 join 함수로 쓰레드가 끝날 때까지 기다린다. 위의 코드의 실행 시간은 <strong>약 4.6초</strong>가 걸렸다.

다음으로 쓰레드를 추가해서 병렬도 동작하는 코드를 만들어보자.

```
if __name__ == "__main__":
    START, END = 0, 100000000
    result = list()
    th1 = Thread(target=work, args=(1, START, END//2, result))
    th2 = Thread(target=work, args=(2, END//2, END, result))
    
    th1.start()
    th2.start()
    th1.join()
    th2.join()

```

th2 를 추가했고, 쓰레드에서 실행되는 함수에 들어가는 인자를 절반씩 나누어 입력하여 따로 계산하도록 했다. 이 코드를 실행하면 하나의 프로세스에서 동작하지만 여러 cpu를 가지고 있다면 쓰레드가 적절히 분산되어 병렬 처리를 할 것이다. 계산 결과는 위와 같았고 실행 시간은 <strong>4.6</strong>초가 걸렸다.

응? 4.6초? 이상하다. 이전에 하나의 쓰레드로 동작시킨 것과 별반 다르지 않다.

이는 파이썬의 GIL 정책 때문이다.

### GIL(Global Interpreter Lock)

언어에서 자원을 보호하기 위해 락(Lock) 정책을 사용하고 그 방법 또한 다양하다. 파이썬에서는 하나의 프로세스 안에 모든 자원의 락(Lock)을 글로벌(Global)하게 관리함으로써 한번에 하나의 쓰레드만 자원을 컨트롤하여 동작하도록 한다.

위의 코드에서 result 라는 자원을 공유하는 두 개의 쓰레드를 동시에 실행시키지만, 결국 GIL 때문에 한번에 하나의 쓰레드만 계산을 실행하여 실행 시간이 비슷한 것이다.

GIL 덕분에 자원 관리(예를 들어 가비지 컬렉팅)를 더 쉽게 구현할 수 있었지만, 지금처럼 멀티 코어가 당연한 시대에서는 조금 아쉬운 것이 사실이다. 그렇다고 파이썬의 쓰레드가 쓸모 없는 것은 아니다. GIL이 적용되는 것은 cpu 동작에서이고 쓰레드가 cpu 동작을 마치고 I/O 작업을 실행하는 동안에는 다른 쓰레드가 cpu 동작을 동시에 실행할 수 있다. 따라서 cpu 동작이 많지 않고 I/O동작이 더 많은 프로그램에서는 멀티 쓰레드만으로 성능적으로 큰 효과를 얻을 수 있다.

### Multiprocessing 모듈로 멀티 프로세스 구현하기

이러한 상황에서 계산을 병렬로 처리하는데 도움을 주는 것이 바로 multiprocessing 모듈이다. multiprocessing 모듈은 쓰레드 대신 프로세스를 만들어 병렬로 동작한다. 위의 계산 프로그램을 멀티 프로세스로 구현한 코드는 다음과 같다.

```
from multiprocessing import Process, Queue

def work(id, start, end, result):
    total = 0
    for i in range(start, end):
        total += i
    result.put(total)
    return

if __name__ == "__main__":
    START, END = 0, 100000000
    result = Queue()
    th1 = Process(target=work, args=(1, START, END//2, result))
    th2 = Process(target=work, args=(2, END//2, END, result))
    
    th1.start()
    th2.start()
    th1.join()
    th2.join()

    result.put('STOP')
    total = 0
    while True:
        tmp = result.get()
        if tmp == 'STOP':
            break
        else:
            total += tmp
    print(f"Result: {total}")
```

multiprocessing 모듈의 가장 큰 장점은 threding 모듈과 구현 방식이 거의 같아서 기존에 쓰레드 방식으로 구현한 코드를 쉽게 이식할 수 있다는 점이다. 위의 코드에서 변경된 것은 Thread 함수가 아닌 Process 함수에서 객체를 받아 사용하는 것과 result로 Queue 객체를 사용한 것뿐이다. 해당 코드를 실행하면 실행시간이 약 <strong>2.6초</strong>로 현저하게 감소한 것을 확인할 수 있다.

프로세스는 각자가 고유한 메모리 영역을 가지기 때문에 쓰레드에 비하면 메모리 사용이 늘어난다는 단점이 있지만, 이 방식을 통해 싱글 머신 아키텍처로부터 여러 머신을 사용하는 분산 애플리케이션으로 쉽게 전환할 수 있다.

각각의 프로세스가 자신만의 메모리 공간을 사용하기 때문에 프로세스간 데이터 교환을 위해 multiprocessing.Queue 객체를 사용해야 한다. multiprocessing 모듈에서는 Queue 이외에도 Pipe 객체를 지원하여 데이터 교환을 돕는다.

### Thread vs Process

결론적으로 말하자면, 파이썬에서 병렬처리를 구현하는 방식은 두가지로 멀티 쓰레드를 사용하거나 멀티 프로세스를 사용하는 것이다. 쓰레드는 가볍지만 GIL로 인해 계산 처리를 하는 작업은 한번에 하나의 쓰레드에서만 작동하여 cpu 작업이 적고 I/O 작업이 많은 병렬 처리 프로그램에서 효과를 볼 수 있다.

프로세스는 각자가 고유한 메모리 영역을 가지기 때문에 더 많은 메모리를 필요로 하지만, 각각 프로세스에서 병렬로 cpu 작업을 할 수 있고 이를 이용해 여러 머신에서 동작하는 분산 처리 프로그래밍도 구현할 수 있다.

각자의 장단점을 고려하여 자신의 프로그램에 잘 맞는 방식을 사용하자.











### 참고사이트

- https://wikidocs.net/82581
- https://monkey3199.github.io/develop/python/2018/12/04/python-pararrel.html


