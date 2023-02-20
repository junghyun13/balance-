# balance-
# c
양팔저울과 추가 있는데 첫째 줄에는 저울추의 개수를 나타내는 양의 정수 N이 주어진다. 둘째 줄에는 저울추의 무게를 나타내는 N개의 양의 정수가 빈칸을 사이에 두고 주어진다. 저울과 추를 이용해서 잴수 없는 가장 작은 수는 얼마인지 구하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>
#include <string.h>


void main(){
	int n,weight[100],i,j,target;
	scanf("%d",&n);
	for(i=0;i<n;i++){
		scanf("%d",&weight[i]);}
	for(i=0;i<n;i++){
		for(j=0;j<n-(i+1);j++){
			int tmp;
			if(weight[j]>weight[j+1]){ //추를 오름차순의 형태로 정렬해서 저장해둔다! 
				tmp=weight[j];
				weight[j]=weight[j+1];
				weight[j+1]=tmp;} }  }
	target=1; //시작은 무게를 1부터 
	for(i=0;i<n;i++){
		if(weight[i]>target){ //추가 타켓으로한  숫자보다 더 크다면  
			break;}
		target=target+weight[i]; } //가장 작은 값들을 누적해나간다  
	printf("주어진추로 측정할수 없는 정수무게중의 최솟값은: %d\n",target); }
