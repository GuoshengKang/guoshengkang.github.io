### C Programming Homework and Answer

#### 【2020/02/24】请编程输出“我的第一个C语言程序"
```c
#include <stdio.h>
int main( )
{	
    printf("这是我的第一个C语言程序\n");
    return 0;
} 
```
#### 【2020/02/28】 编程输出：1、88和125的和; 2、任意输入两个整数，求两数的差。
```c
#include <stdio.h>
int main( )
{	
	int a,b;
	printf("88+125=%d\n",88+125);
    printf("请输入两个整数：");
	scanf("%d %d",&a,&b);
	printf("%d-%d=%d\n",a,b,a-b);
    return 0;
} 
```
#### 【2020/03/05】任意输入一位3位正整数，输出它的逆序数，如输入264，输出462（提示可以用/，%两个运算符）
```c
#include <stdio.h>
int main( )
{	
	int n,gewei,shiwei,baiwei,r;
    printf("请输入一个三位正整数：");
	scanf("%d",&n);
	baiwei=n/100;
	shiwei=n%100/10;
	gewei=n%10;
	r=gewei*100+shiwei*10+baiwei;
	printf("%d逆序数为：%d\n",n,r);
    return 0;
} 
```
#### 【2020/03/09】请模拟实现一个简单的四则运算计算器的功能。即输入一个两个数的运算式，根据不同的运算符得到不同的结果(分别用if和switch结构实现)。提示：1、四则运算指加减乘除;2、有除法运算结果会有小数，考虑变量的数据类型设什么合适
```c
#include <stdio.h>
main( )
{	float x,y;
	char op;
	printf("Please input Expression:");
	scanf("%f%c%f",&x,&op,&y);
	switch(op)
	{	case '+':
		printf("%g%c%g=%g\n", x,op,y,x+y);
			break;
		case '-':
			printf("%g%c%g=%g\n",x,op,y,x-y);
			break;
		case '*':
			printf("%g%c%g=%g\n",x,op,y,x*y);
			break;
		case '/':
			if ((y>=-1e-6) && (y<=1e-6))
				printf("Division Error!\n");
			else
				printf("%g%c%g=%g\n",x,op,y,x/y);
			break;
		default:printf("Expression Error!\n");
	}
}
```
#### 【2020/03/16】编程打印出所有的“水仙花数”。所谓水仙花数：是指一个三位数，其各位数字的立方之和等于该数。 
```c
#include <stdio.h>
int main( )
{ 
	int n,a,b,c; 
	for(n=100; n<1000; n++)
	{
		a=n/100; 
		b=n/10%10; 
		c=n%10; 
		if(a*a*a+b*b*b+c*c*c==n)
			printf("水仙花数有：%5d\n",n);
	}
	return 0;
}
```
#### 【2020/03/20】编程实现从键盘输入一整数，如果该整数为素数，则返回1，否则返回0。要求单独编写一个求素数的自定义函数。
```c
#include <stdio.h>
int fun(int x)
{
	int n;
	for(n=2; n<x; n++)
		if(x%n==0)  
			return 0;
	return  1;
}
int main(void)
{
	int x;
	printf("input a number:");
	scanf("%d", &x);
	if(fun(x))
		printf("%d is a prime number!\n",x);
	else 
	printf("%d is not a prime number!\n",x);
    return 0;
} 

```
#### 【2020/03/23】试用递归的方法编写一个返回长整型的函数，以计算斐波纳契数列的前20项。该数列满足：F(0)=1，F(1)=1，F(n)=F(n-1)+F(n-2)  （n>2）。
```c
#include <stdio.h>
long int Fibonacci (int n)
{
	long int p;
	if(n==0||n==1)
		p=n;
	else
		p= Fibonacci (n-1)+ Fibonacci (n-2);
	return  p;
}
int  main(void)
{
	int n;
	for(n=1; n<=20; n++)
	{
		printf("%-8d", Fibonacci (n));
		if((n)%5==0)
			printf("\n");
	}
    return 0;
} 
```
#### 【2020/03/27】编写一函数change(x，r)，将十进制整数x转换成r（1<r<10）进制后输出。(建议在main函数中调用进行测试)
```c
#include<stdio.h>
#include<math.h>
int change(int x,int r)
{
	int temp, result=0,count=0;
	do
	{
		temp=x%r;
		result=result+temp*pow(10,count++);
		x=x/r;
	}while(x);
	return result;
}
int  main(void)
{
	int x,r;
	printf("请输入一个正整数x:");
	scanf("%d", &x);
	printf("请输入一个正整数r(1<r<10):");
	scanf("%d", &r);
	printf("%d转化为%d进制为:%d\n",x,r,change(x,r));
    return 0;
} 
```
#### 【2020/03/30】如果一个数等于其所有真因子（不包括其本身）之和，则该数为完数，例如：6的因子有1、2、3，且6=1+2+3，故6为完数，求2\~1000中的所有完数。（要求：定义一个函数判断一个数是否为完数，并在main函数中调用，输出2\~1000中的所有完数）
```c
#include <stdio.h>
int IsWanshu(int n)
{
	int k, s=0;
	for(k=1; k<n; k++)
		if(n%k==0)
			s=s+k;
		if(s==n)
			return 1;
		else
			return 0;
}
int  main(void)
{
	int i, j=0;
	for(i=2; i<=1000; i++)
	{
		if(IsWanshu(i))  
		{
			printf("%5d", i);
			j=j+1; 
			if(j%5==0)
				printf("\n");
		}
	}
	printf("\n");
	return 0;
}
```
#### 【2020/04/03】编一程序用简单选择排序方法对10个整数排序（从大到小）。排序思路为：首先从n个整数中选出值最大的整数，将它交换到第一个元素位置，再从剩余的n-1个整数中选出值次大的整数，将它交换到第二个元素位置，重复上述操作n次后，排序结束。
```c
#include <stdio.h>
#define N 10
int  main(void)
{
	int i,j,max,temp,a[N]={29,37,12,30,45,47,27,39,16,72};
	for(i=0; i<N-1; i++)
	{
		max=i;
		for(j=i+1;j<N;j++)
			if(a[j]>a[max])
				max=j;
		temp=a[i];
		a[i]=a[max];
		a[max]=temp;
	}
	for(i=1;i<N;i++)
		printf("%d ",a[i]);
	printf("\n");
	return 0;
}
```