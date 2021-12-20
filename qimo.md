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
### 二、统计次数
* 以回车为结束符的字符串输入：使用`Gets(<数组>)`函数
* 遍历数组，可以判断是否遍历到数组的终值'\0'
```c
#include <stdio.h>
#include <string.h>

int main(){
	int i,x=0;			//x是该字符出现的次数，初始为0 
	char a[80],f[0];		//gets只能给数组赋值 
	gets(a);
	gets(f);
	
	for(i=0;a[i] != '\0' ;i++){	//用'\0'来判断数组是否结束,'\0'是数组结尾 
		if(a[i] == f[0]){
			x++;
		}
	}

	printf("%d\n",x);
	for(i=0;a[i] != '\0';i++){
		printf("%c",a[i]);
	}
}
```
