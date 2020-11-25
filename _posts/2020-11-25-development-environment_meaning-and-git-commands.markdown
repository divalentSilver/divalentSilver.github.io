---
layout: post
title:  "개발환경 의미, 기초 Git 명령어"
date:   2020-11-25
categories: [CISCO, DEVASC, Git]
comments: true
---

오늘은 [What is a Development Environment, and why do you need one?][1]랑 [A Brief Introduction to Git][2]를 봤다.   

### Development Environment   
* Development Environment = (개인이 개발을 하기 위해 사용하는) Software + Tools + Configurations + Setups   
* local/hosted/cloud based   
* tool 추천(stury material에서 사용하는 것)
	* OS: Linux/Windows/Mac OS
	* Source Control Systems: git
	* Terminals and Shells: bash
	* Programming language: Python, Node.js
	* Text Editors and IDE: Atom, Visual Studio Code
	* Development Tolls and Clients: Postman, ngrok, Google Chrome
	* VPN client: CISCO AnyConnect, OpenConnect
	* Application Container Engine: Docker   

### Git 명령어 모음
```sh
$ git clone YOUR_REPOSITORY_URL
$ git status
$ git diff
$ git fetch
$ git pull
$ git branch
$ git branch NEW_BRANCH_NAME //새로운 브랜치 생성
$ git checkout ANOTHER_BRANCH_NAME //해당 브랜치로 전환
$ git checkout -b NEW_BRANCH_NAME //새로운 브랜치 생성 후 해당 브랜치로 전환
$ git merge ANOTHER_BRANCH_NAME //해당 브랜치를 현재 브랜치에 머지
$ git branch --delete --force YOUR_BRANCH_NAME

$ git reset FILE_NAME //Staged -> Modified
$ git checkout FILE_NAME //Modified -> Unmodified

$ git reset --soft //Unmodified -> 커밋 전 Staged
$ git reset --mixed //Unmodified -> 커밋 전 Modified
$ git reset --hard //Unmodified -> 커밋 전 Unmodified

$ git add PATH_TO_YOUR_FILE
$ git commit -m "YOUR_COMMIT_MESSAGE"
$ git push YOUR_REPOSITORY_NAME YOUR_BRANCH_NAME

```

참고:
```
Unmodified -> Modified -> Staged
```

[1]: https://developer.cisco.com/learning/lab/dev-what/step/1
[2]: https://developer.cisco.com/learning/lab/git-basic-workflows/step/1
