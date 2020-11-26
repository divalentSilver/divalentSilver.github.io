---
layout: post
title:  "기초 Python"
date:   2020-11-26
categories: [CISCO, DEVASC, Python]
comments: true
---

오늘은 [Intro to Python - Part 1][1]를 봤다.   
정리 해두고싶은 것들만 기록했다.   

### Python virtual environment
Python 가상 환경이 필요한 이유는 `pip install`으로 패키지 설치를 할 때 global하게 설치된다.   
계속 이런식으로 설치하다보면 conflict가 발생할수도 있어서 각 프로젝트마다 가상 환경을 따로 두는 것이 편리하다.   

python3-virtualenv설치 및 Python 가상 환경 생성:
```sh
$ sudo aptinstall python3-virtualenv
$ python3 -m venv py3-venv
```
Python 가상 환경 활성화:
```py
$ source py3-venv/bin/activate
```
Python 가상 환경 비활성화:
```py
$ deactivate
```
이제 py3-venv 디렉토리 안에 bin과 lib라는 디렉토리가 생성되어있다.   
앞으로 `pip install`로 라이브러리를 설치하면 lib 디렉토리 하위에, executable 스크립트를 설치하면 bin 디렉토리 하위에 설치된다.   

### Python interactive shell / Python script
Python interactive shell에 access:
```sh
$ python -i
```
Python interactive shell을 exit:
```py
$ exit()
```
Python script를 run:
```sh
$ python PATH_TO_YOUR_PYTHON_FILE
```

### Python basics
type 알아내기:
```py
>>> type("What is the type of this?")
<class 'str'>
```
Input:
```py
>>> answer = input("Questions?")
Questions?No.
>>> answer
'No.'
```
Output:
```py
>>> counts = 6
>>> print("There are", counts, "candies.")
There are 6 candies.
```


[1]: https://developer.cisco.com/learning/lab/intro-python-part1/step/1
[2]: https://developer.cisco.com/learning/lab/intro-python-part2/step/1
