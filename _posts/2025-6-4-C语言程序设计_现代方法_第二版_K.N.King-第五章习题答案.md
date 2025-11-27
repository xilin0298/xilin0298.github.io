---
layout: article
title: 2025-6-4-C语言程序设计_现代方法_第二版_K.N.King-第五章习题答案
---
## 练习题
### 5.1节 1
（a）1
（b）1
（c）1
（d）0
### 5.1节 2
（a）1
（b）1
（c）1
（d）1
### 5.1节 3
（a）i < j 判定为1 后面表达式短路
（b）i - 7判定为0 后面表达式短路
（c）将j的值赋给i 后面短路
（d）++i后面短路
### 5.1节 4
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	// 编写一个表达式，要求这个表达式根据 i 小于、等于、大于 j 这 3 种情况，分别取值为 - 1、0、 + 1。
	int i = 1;
	if (i < 3) {
		printf("-1\n");
	} else if(i==3) {
		printf("0\n");
	} else {
		printf("1\n");
	}
}
```
### 5.2节 5
不合法；短路
### 5.2节 6
这道题的意思是用-表示范围，是不合法的，如果合法，if语句判断条件不成立，会跳过
### 5.2节 7
17；17
### 5.2节 8
将两个条件表达式用逻辑符号合为一个即可
### 5.2节9
显而易见是等价的
### 5.3节 10
输出case1后的所有语句，包括case2
### 5.3节 11
略
## 编程题
### 1
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int i;
	printf("Enter an number: ");
	scanf("%d", &i);
	if(i>=0 && i<=9)
		printf("The number %d has 1 digits", i);
	else if(i >= 10 && i <= 99)
		printf("The number %d has 2 digits", i);
	else if (i >= 100 && i <= 999)
		printf("The number %d has 3 digits", i);
}
```
### 2
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int hour,minute;
	printf("Enter a 24-hour time: ");
	scanf("%d:%d", &hour,&minute);
	if(hour>12 && hour<24)
		printf("Equivalent 12-hour time: %d:%d PM ", hour-12,minute);
	else if(hour > 0 && hour <= 12)
		printf("Equivalent 12-hour time: %d:%d AM ", hour, minute);
	else if (hour == 24)
		printf("Equivalent 12-hour time: 00:%d AM ", minute);
}
```
### 3
略
### 4
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float v;
	printf("Enter a speed: ");
	scanf("%f", &v);
	if(v>=1 && v<=3)
		printf("Light air\n");
	else if (v >= 4 && v <= 27)
		printf("Breeze\n");
	else if (v >= 28 && v <= 47)
		printf("Gale\n");
	else if (v >= 48 && v <= 63)
		printf("Storm\n");
	else if (v > 63)
		printf("Hurricane\n");
	else if (v < 1 )
		printf("Calm\n");
	
}
```
### 5
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float income;
	printf("Enter income: ");
	scanf("%f", &income);
	if (income <= 750)
		printf("tax:%f\n",income * 0.01);
	else if(income > 750 && income <= 2250)
		printf("tax:%f\n",7.5+(income-750)*0.02);
	else if (income > 2250 && income <= 3750)
		printf("tax:%f\n", 37.5 + (income - 2250) * 0.03);
	else if (income > 3750 && income <= 5250)
		printf("tax:%f\n", 82.5 + (income - 3750) * 0.04);
	else if (income > 5250 && income <= 7000)
		printf("tax:%f\n", 142.5 + (income - 5250) * 0.05);
	else if (income > 7000 )
		printf("tax:%f\n", 230 + (income - 7000) * 0.06);
}
```
### 6
略
### 7
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int a,b,c,d;
	scanf("%d %d %d %d", &a,&b,&c,&d);

	if(a>b && a>c && a>d) {
		printf("max:%d\n", a);
	} else if(b>a && b>c && b>d) {
		printf("max:%d\n", b);
	} else if(c>a && c>b && c>d) {
		printf("max:%d\n", c);
	} else {
		printf("max:%d\n", d);
	}

	if (a < b && a < c && a < d) {
		printf("min:%d\n", a);
	}
	else if (b < a && b < c && b < d) {
		printf("min:%d\n", b);
	}
	else if (c < a && c < b && c < d) {
		printf("min:%d\n", c);
	}
	else {
		printf("min:%d\n", d);
	}
}
```
### 8
略
### 9
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int mm, dd, yy,mm1,dd1,yy1;
	printf("Enter first date (mm/dd/yy): ");
	scanf("%d/%d/%d", &mm, &dd, &yy);
	printf("Enter second date (mm/dd/yy): ");
	scanf("%d/%d/%d", &mm1, &dd1, &yy1);
	if(yy>yy1 || (yy==yy1 && mm>mm1) || (yy==yy1 && mm==mm1 && dd>dd1))
		printf("%02d/%02d/%02d is later than %02d/%02d/%02d\n", mm, dd, yy, mm1, dd1, yy1);
	else if( yy < yy1 || (yy == yy1 && mm < mm1) || (yy == yy1 && mm == mm1 && dd < dd1) )
		printf("%02d/%02d/%02d is later than %02d/%02d/%02d\n", mm1, dd1, yy1, mm, dd, yy);
	else
		printf("Both dates are the same: %02d/%02d/%02d\n", mm, dd, yy);
	return 0;
}
```
### 10
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int grade;
	printf("Enter your grade: ");
	scanf("%d", &grade);
	int ten_digit = grade / 10;
	switch (ten_digit) {
		case 10:
			printf("A");
			break;
		case 9:
			printf("A");
			break;
		case 8:
			printf("B");
			break;
		case 7:
			printf("C");
			break;
		case 6:
			printf("D");
			break;
		default:
			printf("F");
			break;
	}
		
}
```
### 11
略
