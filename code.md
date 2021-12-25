# 一些基础的算法
## 分数的累加
* 1/3-3/5+5/7-7/9…+17/19-19/21
* **每次运算的符号变化**<br>
    定义一个flag来控制，用flag的正负来控制。
* **含小数的运算**<br>
    不止sum是包含小数，i/(i+2)也涉及到了小数，所以i也定义为double
```c
#include <stdio.h>
int main(){
	double flag=1,i,sum=0;
	
	for(i=1;i<=19;i=i+2){
		sum=sum + flag*i/(i+2);
		flag=-flag;
	}
	
	printf("%f",sum);
} 
```
