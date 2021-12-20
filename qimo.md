# 期末复习
### 一、寻找x
* 创建数组并赋值
* 输入x并设置默认寻找状态标识为没找到
* 遍历数组 判断x与数组内容 并且设置找到后的状态标识
```c
#include <stdio.h>
int main(){
	
	int n,m,x,a[100][100],i,j,f;
	scanf("%d %d",&n,&m);
	
	for(i=0;i<n;i++){
		for(j=0;j<m;j++){
			scanf("%d",&a[i][j]);
		}
	}
	
	scanf("%d",&x);
	f=0;
	
	for(i=0;i<n;i++){
		for(j=0;j<m;j++){
			if(x==a[i][j]){
				printf("%d %d",i,j);
				f=1;		
			}
		}
	}
	
	if(f==0){
		printf("Not Found");
	}
}
```
