```c++
#include <iostream>
#include <string.h>
using namespace std; 
/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main(int argc, char** argv) {
	int N=0,temp=0;
	char number[50][50],temparr[1][50];
	int i=0,j=0,k=0,l=0,a=0,b=0;
	int judge=0;
	int flag=0;
	memset(number,'0',sizeof(number));
	
	cin>>N;
	for(i=0;i<N;i++){
		scanf("%s",number[i]);
	}
	
	for(i=0;i<N;i++){
		for(j=i+1;j<N;j++){
			
			judge=strcmp(number[i],number[j]);
			
			//cout<<judge<<endl;
			if(judge==-1){
				strcpy(temparr[0],number[j]);
				strcpy(number[j],number[i]);
				strcpy(number[i],temparr[0]);
			}
		}
	}//先进行一次比较，按照顺序的大小比较出结果来 
	for(i=0;i<N;i++){
		for(j=i+1;j<N;j++){
			//规定i数大于j数
			 
			flag=0;
			//cout<<number[i]<<"   "<<number[j]<<endl;
			//cout<<strlen(number[i])<<"   "<<strlen(number[j])<<endl;
			if(strlen(number[i])<strlen(number[j])){
				//大的数短 
				for(l=0;flag==0;l++){
					for(k=0+l*strlen(number[i]);((k<(strlen(number[i])+l*strlen(number[i])))&&(k<strlen(number[j])));k++){
						if(number[i][k]<number[j][k]){
							 
							strcpy(temparr[0],number[j]);
							strcpy(number[j],number[i]);
							strcpy(number[i],temparr[0]);
							break;
							flag=1;
						}else if(number[i][k]>number[j][k]){
							break;
							flag=1;
						}
					}
					if(k==strlen(number[j])-1){
						flag=1;
					}
				}//727273和72 
			}
			if(strlen(number[i])>strlen(number[j])){
				//cout<<'2'<<endl;
				for(l=0;flag==0;l++){
					//cout<<'3'<<endl;
					for(k=0+l*strlen(number[j]);((k<(strlen(number[j])+l*strlen(number[j])))&&(k<strlen(number[i])));k++){
						if(number[i][k]<number[j][k]){
							strcpy(temparr[0],number[j]);
							strcpy(number[j],number[i]);
							strcpy(number[i],temparr[0]);
							break;
							flag=1;
						}else if(number[i][k]>number[j][k]){
							break;
							flag=1;
						}
					}
					if(k==strlen(number[i])-1){
						flag=1;
					}
				}
			}
		}
	}
	for(i=0;i<N;i++){
		printf("%s",number[i]);
	}
	return 0;
}
```

