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
## m!和n!（阶乘）
* 输入m和n，计算m！和n！之和
* **定义阶乘**<br>
    需要阶乘的累加数，这个数开始必须是1，如此累乘m或n次。
```c
#include <stdio.h>
int main()
{
    int i,n,m,fm=1,fn=1;
    scanf("%d %d",&m,&n);
    
    for(i=1;i<=m;i++){		//阶乘算法块
        fm=fm*i;
    }
    for(i=1;i<=n;i++){
        fn=fn*i;
    }
    
    printf("%d\n",fm+fn);
}

```
