---
layout: article
title: C语言程序设计_现代方法_第二版_K.N.King-第三章习题答案
---

## 练习题
### 3.1节1
（a）输出是
```
····86，1040
```
（b）输出是
```
·3.02530e+01 
```
(c)输出是
```
83.1620
```
(d)输出是
```
1e-06·
注意这里，转换指定符为g时，p是可以显示的有效数字
```
具体过程如下：
- 指数精度绝对值大于4，使用%e转换指示符
- 即9.979e-7,因为p=2，所以结果是10e-7
- 科学计数法为1.0e-6
- 1.0e-6中的.0被转换指示符g认为是无效的尾随0，所以结果为1e-6
- 总之，转换指示符g是为了紧凑而服务的

### 3.1节2
（a）
```c
printf("%-8.1e",x);
```
(b)
```c
printf("%10.6e",x);
```
(c)
```c
printf("%-8.3f",x);
```
(d)
```c
printf("%6.0e",x);
注意这里直接写%6f会默认小数点后6位保留
```
### 3.2节3
（a）等价
（b）等价
（c）不等价，%f·末尾的空格表示读取并丢弃所有后续的空白字符，直到遇到一个非空白字符
（d）等价
### 3.2节4
i的值是10
x的值是0.3
j的值是5
### 3.2节5
x的值是12.3
i的值是45
y的值是0.6
### 3.2节6
类似于
```c
scanf("%d / %d", &num1, &denom1);
```
可以实现
```c
1/2
1 /2
1/ 2
1 / 2
```
## 编程题
### 1
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int mm, dd, yyyy;
	printf("Enter date (mm dd yyyy): ");
	scanf("%d/%d/%d", &mm, &dd, &yyyy);
	if (mm >= 10)
	{
		printf("You entered the data %d%d%d\n", yyyy, mm, dd);
	}
	else
	{
		printf("You entered the data %d0%d%d\n", yyyy, mm, dd);
	}
}
```
### 2
```c
 #define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int item;
	float price;
	int mm, dd, yyyy;
	printf("Enter item number: ");
	scanf("%d", &item);
	printf("Enter unite price: ");
	scanf("%f", &price);
	if (price > 9999.99)
	{
		printf("Error: Price must be less than 9999.99\n");
	}
	else {
		printf("Enter purchase date (mm/dd/yyyy): ");
		scanf("%d/%d/%d", &mm, &dd, &yyyy);
		printf("\nItem\tUnit Price\tPurchase Date\n");
		if (mm >= 10) {
			printf("%d\t$%.2f\t\t%2d/%d/%d\n", item, price, mm, dd, yyyy);
		}
		else {
			printf("%d\t$%.2f\t\t0%d/%d/%d\n", item, price, mm, dd, yyyy);
		}
		 
	}
}
```
### 3
```
 #define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int GSI, GI, PC, IN, CD;
	printf("Enter the ISBN number (format: GSI-GI-PC-IN-CD): ");
	scanf("%d-%d-%d-%d-%d", &GSI, &GI, &PC, &IN, &CD);
	printf("GSI PREFIX: %d\n", GSI);
	printf("GROUP Identifier: %d\n", GI);
	printf("PUBLISHER Code: %d\n", PC);
	printf("ITEM Number: %d\n", IN);
	printf("CHECK DIGIT: %d\n", CD);
}
```
### 4
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int a, b, c;
	printf("Enter phone number [(xxx) xxx-xxxx]: ");
	scanf("(%d) %d-%d", &a, &b, &c);
	printf("You entered: %d.%d.%d\n", a, b, c);
}
```
### 5
略
### 6
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main() {
	int num1, denom1, num2, denom2, result_num, result_denom;
	printf("Enter two fractions seperated by a plus sign: ");
	scanf("%d/%d+%d/%d", &num1, &denom1, &num2, &denom2);
	result_num = num1 * denom2 + num2 * denom1;
	result_denom = denom1 * denom2;
	printf("The sum is %d/%d\n", result_num, result_denom);
}
```