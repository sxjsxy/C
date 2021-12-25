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

## 素数的各位数字之和
* 对于每个整数，若不是素数，则输出0，否则，输出该素数的各位数字和。
* **判断是否为素数**<br>
    素数只能被自身和1整除，所以用for来循环除一次
* **取得个位数的值**<br>
    用n%10进行取余，即可得到个位数的值
```c
#include <stdio.h>
#include <math.h>   
int main(){   
	int i, m, n,g,sum=0; 
	scanf("%d",&n);    
    
	m = sqrt(n);				//sqrt(n)可以减少循环次数，因为被开方了
    
	for (i = 2; i <= m; i++){	//只被1或自身整除，所以从2开始除 
		if(n % i == 0) {		//如果被整除了，那么就跳过这个数
			printf("0\n");		//在循环的最后i=m时，如果这个循环跑完了，那么i会+1 
			break;				//i=m+1
		} 						//所以此时可以用i>m判断是否跑完循环(是否被整除了)
	}							//来进行判断是否为素数
    							 
	if(i > m){ 					  
		while(n!=0){ 			//如果这个数没有被除完，就一直除 
			g=n%10;				//取余，得到个位 
			sum=sum+g;			
			n=n/10;				//因为整数机制，所以/10后，十位变个位，个位变0 
		}
		printf("%d\n",sum); 
	}
}
```
