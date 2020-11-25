---
layout: post
title:  "DEVASC 공부를 위한 개발환경 설정"
date:   2020-11-23
categories: [CISCO, DEVASC, Configuration]
comments: true
---
여유가 잠깐 생겨서 CISCO DEVASC 공부를 시작했다.   
[Exam overview][1]를 보면 어떤 내용이 시험에 나오는지 자세히 알 수 있다.   
각 항목마다 Study material이 링크되어있는데, 하나씩 따라해보며 공부하려고 한다.  (로그인해야 볼 수 있다)   
이걸 따라해보다가 발생한 문제 해결법이나 정리할 필요가 있는 개념 등을 앞으로 포스팅하려고 한다.   

오늘은 [Setting up your Linux (Ubuntu) workstation as a development environment][2]를 했다.   

가상머신에 이미 깔려있는 우분투18이 있어서 여기에다 해보고 있으며 기본 Gnome Shell을 그대로 사용중이다.   


### sudo apt install 시 `Could not get lock /var/lib/dpkg/lock-frontend` 에러 해결 방법   
뭔가를 sudo apt install 할 때 가끔씩 `Could not get lock /var/lib/dpkg/lock-frontend` 에러가 발생했다.   
다른 명령어나 앱으로 인해 소프트웨어 install 또는 update 중일 때 dpkgfile이 lock되는데, 여러 프로세스가 동시에 같은 파일을 수정하지 않게 하려고 이런 lock이 걸린다고 한다.   
이 때, 아래와 같은 절차를 진행하면 대부분 해결되었다.   

실행중인 프로세스를 모두 kill:   
```sh
$ sudo killall apt apt-get
```
실행중인 프로세스가 없다고 나오면 lock 걸린 디렉토리 삭제 후, configure 및 update:   
```sh
$ sudo rm /var/lib/apt/lists/lock
$ sudo rm /var/cache/apt/archives/lock
$ sudo rm /var/lib/dpkg/lock*
$ sudo dpkg --configure -a
$ sudo apt update
```


### OpenConnect 설치 후 VPN 서버에 연결 되는지 확인하는 방법
[DevNet Sandbox Catalog][3]에서 sandbox 하나를 골라서 reserve하면 여기에 연결할 수 있는 VPN 서버를 하나 제공해준다. (4시간 한정)   
Activate될 때까지 15분 정도 소요되며, 다 되면 이메일로 VPN 서버 주소, username, password를 알려준다.   
OpenConnect를 통해 여기로 연결이 잘 되는지 확인해보면 된다:
```sh
$ sudo openconnect -b YOUR_VPN_ADDRESS
```


[1]: https://developer.cisco.com/certification/exam-topic-associate/
[2]: https://developer.cisco.com/learning/lab/dev-ubuntu/step/1
[3]: https://devnetsandbox.cisco.com/
