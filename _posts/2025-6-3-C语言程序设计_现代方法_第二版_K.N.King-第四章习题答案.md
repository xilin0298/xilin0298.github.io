---
layout: article
title: C语言程序设计_现代方法_第二版_K.N.King-第四章习题答案
---
## 练习题
### 4.1节1
（a）1 2
（b）0
（c）1
（d）0
### 4.1节2
-9/7和-(9/7)都是-1，都会向零取整
### 4.1节3
在C89中，当操作数异号时，商可以**向零取整**或者**向负无穷取整**（即 floor 除法），但在C99中，只有向零取整
（a）1
（b）向零取整 -1 ；向负无穷取整 -2 ；
（c）向零取整 -1 ；向负无穷取整 -2 ；
（d）1
### 4.1节4
（a）1
（b）向零取整 -1
（c）向零取整 -1
（d）1
### 4.1节5
（a）3
（b）-1.6向零取整 -1 余数=-8-（-1）* 5=-3；-1.6向负无穷取整 -2  余数=-8-（-2）* 5=2；
（c）-1.6向零取整 -1 余数=8-（-1）* -5 =3；-1.6向负无穷取整 -2  余数=8-（-2）* -5=-2；
（d）-3
### 4.1节6
（a）3
（b）-1.6向零取整 -1 余数=-8-（-1）* 5=-3；
（c）-1.6向零取整 -1 余数=8-（-1）* -5 =3；
（d）-3
### 4.1节7
略
### 4.1节8
正确
### 4.2节9
（a）63 8
（b）3 2 1
（c）2 -1 3
（d）0 0 0
### 4.2节10
（a）12 12
（b）3 4
（c）2 8
（d）6 9

### 4.3节11
（a）0 1
（b）4 11 6
（c）-2 8 7
（d）3 4 5 4
### 4.3节12
(a)6 16
(b)6 -7
(c)6 23
(d)6 15 
### 4.3节13
++i
### 4.4节14
(a) (a * b) - (c * d) + e
(b) a / b % c / d         * / %都是相同优先级左结合
(c) -a-b+c-d
(d) a * (-b) /c -d
### 4.5节15
(a) i=3;j=2
(b) i=0;j=2
(c) i=1;j=2
(d)i=1;j=3
## 编程题
### 1
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int num;
	printf("Enter a two-digit number: ");
	scanf("%d", &num);
	int tens_digits = num / 10;
	int unit_digits = num % 10;
	printf("The reversal is: %d%d\n", unit_digits,tens_digits );
}
```
### 2
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int num;
	printf("Enter a three-digit number: ");
	scanf("%d", &num);
	int tens_digits = num % 100 / 10;
	int unit_digits = num % 10;
	int hundreds_digits = num / 100;
	printf("The reversal is: %d%d%d\n", unit_digits,tens_digits,hundreds_digits );
}
```
### 3
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int tens_digits ;
	int unit_digits ;
	int hundreds_digits ;
	printf("Enter a three-digit number: ");
	scanf("%1d%1d%1d", &hundreds_digits,&tens_digits,&unit_digits);
	printf("The reversal is: %d%d%d\n", unit_digits,tens_digits,hundreds_digits );
}
```
### 4
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	printf("enter a number between 0 and 32767:");
	int x;
	scanf("%d", &x);
	int last_one = x % 8;
	int secondtolast = x / 8 % 8;
	int thirdtolast =  x / 8 / 8 % 8;
	int fourthtolast = x / 8 / 8 /8 % 8;
	printf("you entered: 0%d%d%d%d\n", fourthtolast, thirdtolast, secondtolast, last_one);

}
```
### 5
略
### 6
略