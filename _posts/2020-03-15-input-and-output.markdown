---
layout: post
title:  "cin/cout을 사용한 입출력 연습"
date:   2020-03-15
categories: [ProblemSolving, C/C++]
comments: true
---
PS 문제를 풀려고 할 때 입출력을 처리하는 부분에서부터 막히는 일이 없도록 하려고 한다.  
다양한 입출력 연습 문제를 풀어보고 정리했다.

## 테스트 케이스 개수 입력 방식에 따른 반복문 구성 방법

### 1) 테스트 케이스 개수가 주어졌을 때

```cpp
#include <iostream>
using namespace std;

int main(){
    int testCase;
    cin >> testCase;
    for(int t=0; t<testCase; t++){
        int a, b;
        cin >> a >> b;
        cout << a+b << "\n";
    }
}
```


### 2) 테스트 케이스 개수가 주어지지 않았을 때

```cpp
#include <iostream>
using namespace std;

int main(){
    int a, b;
    while(cin >> a >> b){
        cout << a+b << "\n";
    }
}
```


### 3) 마지막 테스트 케이스로 특정 값을 입력받을 때 (예: 입력의 마지막에 0 0이 들어옴)

```cpp
#include <iostream>
using namespace std;
int main(){
    int a, b;
    while(cin >> a >> b){
        if (a==0 && b==0){
            return 0;
        }
        cout << a+b << "\n";
    }
}
```


## 테스트 케이스 입출력 (입력 형식 -> 추출하고자 하는 형식)

### 1) 정수와 문자 조합 -> 정수 하나씩 (예: 2,3)

```cpp
#include <iostream>
using namespace std;

int main(){
    int testCase;
    cin >> testCase;
    for (int t = 0; t < testCase; t++){
        int a, b;
        char c;
        cin >> a >> c >> b;
        cout << a+b << "\n";
    }
}
```

### 2) 공백 포함하는 문자열 -> 그대로 (앞 뒤 공백 및 빈 줄도 가능) (예: Divalent Silver)

```cpp
#include <iostream>
using namespace std;

int main(){
    string s;
    while(getline(cin, s)){ //이 부분!
        cout << s << "\n";
    }
}
```

### 3) 공백 없이 이어붙인 숫자들 -> 숫자 하나씩 (예: 2222222) &#10024;

```cpp
#include <iostream>
using namespace std;

int main(){
    int n;
    int sum = 0;
    cin >> n;
    for (int i = 0; i < n; i++){
        char c;
        cin >> c;
        sum += c - 48; //아스키코드 '0'의 값을 뺌
    }
    cout << sum << "\n";
}
```

### 4) 공백 없는 문자열 -> 문자 10개씩 &#10024;

```cpp
#include<cstdio>
using namespace std;
 
int main(){
    char s[101]; //최대 길이 100이라는 조건 필요
    while(scanf("%10s",s)){
        printf("%s\n",s);
    }
    return 0;
}
```

위 방식보다는 효율성이 떨어지나 문자열 최대 길이 조건이 없는 경우 아래 방식 활용

```cpp
#include<iostream>
#include<string>
using namespace std;
 
int main() {
    string s;
    getline(cin, s);
    for (int i = 0; i < s.size(); i++){
        cout << s[i];
        if ((i+1)%10 == 0){
            cout << "\n";
        }
    }
    cout << "\n";
}
```

### 5) To be continued..






---

Task list  
[ ] cin/cout과 scanf/printf 특징 비교
