---
layout: post
title:  "달력 관련 문제"
date:   2020-03-16
categories: [ProblemSolving, C/C++]
comments: true
---
달력과 관련된 문제들을 정리하고 있다.

## 날짜 계산 문제

### 1) [해당 년도 내 주어진 날짜의 요일 구하기][1]
*문제*  
오늘은 2007년 1월 1일 월요일이다. 그렇다면 2007년 x월 y일은 무슨 요일일까? 이를 알아내는 프로그램을 작성하시오.

*입력*  
첫째 줄에 빈 칸을 사이에 두고 x(1≤x≤12)와 y(1≤y≤31)이 주어진다. 참고로 2007년에는 1, 3, 5, 7, 8, 10, 12월은 31일까지, 4, 6, 9, 11월은 30일까지, 2월은 28일까지 있다.

*출력*  
첫째 줄에 x월 y일이 무슨 요일인지에 따라 SUN, MON, TUE, WED, THU, FRI, SAT중 하나를 출력한다.

```cpp
#include <iostream>
using namespace std;

int main(){
    string day[7] = { "SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT" };
	int month[13] = { 0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
    int m, d;
    int totalDays = 0;
    cin >> m >> d;
    for (int i = 1; i <= m; i++){
        if (i == m) totalDays += d;
        else totalDays += month[i];
    }
    cout << day[totalDays%7] << "\n";
}
```

To be continued..

[1]: https://www.acmicpc.net/problem/1924
