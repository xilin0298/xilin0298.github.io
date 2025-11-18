---
layout: article
title: C语言程序设计_现代方法_第二版_K.N.King-第二章习题答案
---

## 练习题
### 2.1节1
在VS2022上运行，并不会产生警告信息，本题的代码中缺少return 0；，可能会出现
```
warning：“main”必须返回一个值
```
有两种解决办法，第一种是将main函数的返回类型改为void，第二种是补充return 0；

### 2.2节2
（a）把预处理器执行的命令叫作指令，所有的指令都是以字符#开头，在本题中，#include <stdio.h>就是一条指令，main函数内部的就是语句
（b）程序的输出是
```
Parkinson's Law:
Work expands so as to fill the time
available for its completion.
(帕金森定律： 工作会不断扩展，直到填满所有可用的完成时间)
```

### 2.4节3
在例子int height = 8;中，按照C语言的术语，数值8就是一个初始化器（initializer），可见所谓初始化器就是在变量声明的同时赋予初始值
缩写程序如下：
```c
#include <stdio.h>
int main() {
	int height = 8,length = 12,width = 10;
	int volume = height * length * width;
	printf("Dimensions:%dx%dx%d\n",length,width,height);
	printf("Volume (cubic inches): %d\n",volume);
	printf("Dimensional weight (pounds): %d\n",(volume + 165) / 166);
	
	return 0;
}
```

### 2.4节4
因为变量分配在栈上，栈内存会被重复使用，所以未被赋值的变量显示的值可能是被其他函数中的变量使用过的值，另外不同OS对内存初始化策略不同，安全增强的系统可能会用特定值填充未初始化的内存。

### 2.7节5
（a）不合法，以数字开头
（b）虽合法，但以下划线开头常用在系统库或内部变量，代码中谨慎使用
（c）合法，下划线数量可以连用
（d）合法

### 2.7节6
很简单的原因，因为很难看清有几个下划线连用

### 2.7节7
（a）（e）是关键字
（c）（d）是函数名
（b）是变量名

### 2.8节8
14个记号

### 2.8节9
```
answer = ( 3 * q - p * p) / 3;
无硬性要求，按照书中建议，指令单独成行，标点符号前后空一格，语句前适当缩进，用空行将代码分为若干逻辑单元等
```

### 2.8节10
参照2.8节9答案建议

## 编程题
1.代码如下
```c
#include <stdio.h>
int main() {
	printf("       *\n");
	printf("      *\n");
	printf("     *\n");
	printf("*   *\n");
	printf(" * *\n");
	printf("  *\n");

	return 0;
}
```

2.代码如下：
```c
#include <stdio.h>
int main() {
	float r = 10.0f;
	float v = 4.0f / 3.0f * 3.1415926f * r * r * r;
	printf("v = %.1f",v);

	return 0;
}
```
3.代码如下：
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float r,v;
	scanf("%f", &r);
	v = 4.0f / 3.0f * 3.1415926f * r * r * r;
	printf("v = %.1f",v);

	return 0;
}
```
4.代码如下：
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float amount = 0.0f, total = 0.0f;
	printf("Enter an amount: ");
	scanf("%f", &amount);
	total = amount + amount * 0.05f;
	printf("total: %.2f ",total);
	return 0;
}
```
5.代码如下：
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float x = 0.0f;
	printf("Enter a float number: ");
	scanf("%f", &x);
	float result = 3.0f * x * x * x * x * x +
		2.0f * x * x * x * x - 5.0f * x * x * x - x * x + 7.0f * x - 6.0f;
	printf("result is %.2f ",result);
	return 0;
}
```
6.类似5
7代码如下;
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int amount = 0;
	printf("Enter an amount: ");
	scanf("%d", &amount);
	int x_20 = amount / 20;
	int remainder_20 = amount - x_20 * 20;
	int x_10 = remainder_20 / 10;
	int remainder_10 = remainder_20 - x_10 * 10;
	int x_5 = remainder_10 / 5;
	int remainder_5 = remainder_10 - x_5 * 5;
	int x_1 = remainder_5 / 1;
	printf("$20 bills: %d\n$10 bills: %d\n$5 bills: %d\n$1 bills: %d\n", x_20,x_10,x_5,x_1);

	return 0;
}
```
8.代码如下：
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	float loan;
	printf("Enter loan amount: ");
	scanf("%f", &loan);
	float interest;
	printf("Enter interest rate: ");
	scanf("%f", &interest);
	interest = interest / 100.0f / 12.0f;
	float m_payment;
	printf("Enter monthly payment: ");
	scanf("%f", &m_payment);

	// 注意，还款余额和月利率的乘积中的还款余额是上个月还款后的余额
	float remain_1 = loan - m_payment + loan * interest;
	printf("Balance remaining after first payment: %.2f\n", remain_1);
	loan = remain_1;
	float remain_2 = loan - m_payment + loan * interest;
	printf("Balance remaining after second payment: %.2f\n", remain_2);
	loan = remain_2;
	printf("Balance remaining after third payment: %.2f\n", loan - m_payment + loan * interest);
	return 0;
}
```