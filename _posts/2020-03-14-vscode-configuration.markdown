---
layout: post
title:  "알고리즘 Problem Solving 공부를 위한 개발환경 설정"
date:   2020-03-14
categories: [ProblemSolving, Configuration]
comments: true
---
알고리즘 Problem Solving을 연습해야겠다는 생각이 들어서 공부를 제대로 하기 시작했다.  
먼저 코딩 테스트 환경에 맞춰 개발환경을 세팅했다.  
1. [Visual Studio Code 설치][1]
2. UI를 한글로 바꾸고싶어서 [한국어UI extension 설치][2]
3. [C/C\++ extension 설치][3]
4. gcc를 쓰기 위해 [Mingw 설치하고 configuration하기][4] (여기서 C++98로 설정 가능)

4번 과정에서 링크 걸어둔 페이지에 나오는 것을 차례대로 해보면서 VS Code에서 빌드랑 디버깅하는 방법을 익혔다.  
C\++98로 설정했기 때문에 페이지 말미에 나오는 예제 코드를 아래와 같이 수정해서 해야했다. (중괄호를 이용한 초기화가 불가능함)

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main(){
    vector<string> msg;
    msg.push_back("Hello"), msg.push_back("C++"), msg.push_back("World");
    msg.push_back("from"), msg.push_back("VS Code"), msg.push_back("and the C++ extension!");

    for (const string& word : msg){
        cout << word << " ";
    }
    cout << endl;
}

```

---

Task list  
[V] C\++11에서는 되지만 C\++98에서는 안되는 문법 정리


[1]: https://code.visualstudio.com/Download
[2]: https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-ko
[3]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)
[4]: https://code.visualstudio.com/docs/cpp/config-mingw
