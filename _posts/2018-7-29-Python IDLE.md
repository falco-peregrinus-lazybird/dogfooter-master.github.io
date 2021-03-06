---
layout: post
title: 1. Python IDLE
---

Python 을 사용해서 프로그래밍할 때 좋은 점이 하나 있습니다. 간단한 명령어나 함수를 테스트하고 싶을 때는 Python 에서 제공해주는 "IDLE"이라는 프로그램을 사용하면 됩니다. 이번 포스팅에서는 매크로 프로그램을 만들 때 가장 기초가 되는 "마우스 클릭" 기능을 Python 으로 어떻게 구현할 수 있는 지에 대해서 소개해드리겠습니다.

목표
=

* 마우스로 원하는 좌표 클릭하기

준비물
=

* Microsoft Windows OS가 설치된 개인 컴퓨터. (Windows OS란 우리가 흔히 말하는 윈도우7, 윈도우8, 윈도우10입니다. 특별한 목적을 가지고 컴퓨터를 사용하는 분 외에는 대부분 윈도우가 설치되어 있을 것입니다.)

Python 마우스 제어
=

게임 매크로를 만들려면 가장 먼저 마우스 클릭에 대해서 알아야 합니다. 사실 마우스 클릭만 있어도 정해진 시간마다 정해진 위치를 클릭할 수가 있기 때문에 기본적인 매크로 기능은 할 수 있다고 생각합니다. 매크로 고급 기능으로 가기 위한 첫 걸음이라고 보면 되겠습니다.

구글에서 "파이썬 마우스 제어" 라고 검색해봅니다. Python을 사용한 마우스 제어 방법이 다양하다는 것을 알 수 있습니다. 프로그래밍 관련 구글 검색은 한글보단 영어가 더 좋습니다. 그래서 일단 궁금한 게 생기면 한글로 먼저 검색하고, 검색 결과에서 원하는 답을 찾지 못했을 경우에 영어로 검색하면 됩니다. 마우스 제어 같은 경우에는 한글로도 충분히 답을 찾을 수 있을 것 같군요. 하지만 영어로도 한번 검색을 해봅니다.

```
python mouse cotrol how to
```


<br />

![Alt text](/images/1/1_0.PNG)

<br />

검색 결과, 천만 개 이상이 나옵니다. 

"how to"는 영어로 구글 검색시 필수 단어라고 보시면 됩니다.  한글로 검색한 것과 비슷한 결과를 얻을 수가 있습니다. 여러가지 방법 중에 우리는 일단 PyAutoGui를 사용해서 마우스를 제어해볼 것입니다. 왜냐하면 이게 가장 쉬워보이기 때문입니다.(결과론적인 얘기지만 이게 가장 쉽고 초보적인 단계의 마우스 클릭 기능이었습니다.)

이제 우리는 PyAutoGui로 어떻게 마우스 클릭을 할 수 있을까요? 아니, PyAutoGui 가 뭘까요? Python 하고 다른걸까요?

PyAutoGui는 Python 언어로 우리가 원하는 기능을 누군가가 만들어 놓은 프로그램입니다. 보통 이런 것을 라이브러리라고도 부르는데 우린 그냥 "남들이 이미 해놓은 것"이라고 이해하면 됩니다.  이렇게 남들보다 먼저 만들어놓는 사람들 덕분에 우리는 편하게 마우스 제어를 하게 되는겁니다. 세상 모든 천재분들에게 감사드립니다.

그렇다면 Python으로 어떻게  PyAutoGui를 사용할 수 있을까요? 바로 pip가 그 일을 해줍니다.

윈도우 콘솔창을 엽니다. 콘솔창 여는 방법을 모르겠다면 구글 검색창으로 이동해서 빨리 알아오세요.


```

> pip install pyautogui

```

위와 같이 콘솔창에 입력합니다.

 'python'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.
위와 같이 메세지가 출력된다면 이전 글 [0. How to install Python](https://dogfooter-master.github.io/How-to-install-Python/) 를 참고해서 Python 환경 변수 경로(PATH)를 잘 설정해주세요. 두 개를 설정해야 합니다. python.exe 가 있는 디렉토리와 pip.exe 가 있는 디렉토리.

설치가 잘되고 있다면 바로 알 수 있습니다. pip가 다운로드 진행과 설치를 퍼센트로 알려주거든요.

이제 PyAutoGui 를 사용할 수 있게 되었습니다. 우리는 덕분에 마우스 제어를 어떻게 구현해야할 지에 대해선 신경쓰지 않아도 됩니다. 단지 우리가 알아야 할 것은 마우스 클릭이 하고싶을 때는,

```
pyautogui.click()
```

만 하면 된다는 것입니다.

PyAutoGui 설명서:

[http://pyautogui.readthedocs.io/en/latest](http://pyautogui.readthedocs.io/en/latest)

PyAutoGui
=

이제 마우스 클릭을 한번 테스트해봅시다. 여기서 또 하나의 Python 장점이 나옵니다. 내가 원하는 기능 테스트가 용이하다는 것인데 마우스 클릭을 예로 들면 바로 마우스 클릭에 관련된 코드를 작성하여 테스트를 해볼 수 있습니다.

모든 언어는 기본적으로 편집기를 필요로 합니다. 편집기는 개인 취향에 따라 달라집니다. 어떤 사람은 메모장을 좋아하는가 하면 어떤 사람은 복잡한 기능들이 얽혀있는 편집기를 좋아하기도 합니다. Python 에는 IDLE 이라는 기본 편집기가  제공됩니다. 이 IDLE은 편집기 기능말고도 Python 에서 제공하는 라이브러리들에 대한 간단한 테스트를 빠르게 할 수 있도록 해줍니다.

윈도우 시작 버튼 -> 모든 프로그램 -> Python 3.6 -> IDLE 클릭해줍니다. 아래와 같은 화면이 뜨면 다음으로 넘어갈 수 있습니다.  IDLE 를 실행시키지 못했다면 구글 검색을 활용해서 어떻게든지 꼭 실행시킵니다.


IDLE 를 정상적으로 실행했다면 ">>>" 뒤에 입력이 가능합니다. 아래와 같이 한 줄씩 입력하고 엔터를 쳐줍니다.

```
>>> import pyautogui

>>> pyautogui.click(640,360)
```

import 는 Python 에게 "나는 남이 만들어 놓은 걸 갖다 쓰겠다"라고 말하는 겁니다. 그냥 그렇게 이해하면 됩니다. 여기서는 "남이 만들어 놓은 pyautogui 라이브러리를 가져다 쓰겠다"라는 의미입니다.

두 줄을 입력한 후 엔터를 치면 내 모니터 화면상 좌표 X(가로) Y(세로) (640, 360)로 마우스 커서가 이동한 걸 확인하셨나요? 눈치챘겠지만 마우스 커서가 이동한 뒤 클릭도 한 것입니다. 이걸 확인 하셨다면 이번 목표를 달성한 것입니다.

이제 마우스 클릭을 자동으로 할 수 있게 되었습니다.

수고하셨습니다.

