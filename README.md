# Exchange
交换两个长度相同数组内容
#include <stdio.h>
#include <windows.h>
extern void Exchange(int *arr1, int *arr2, int len);
extern void print(int arr[], int len);
int main(){
	int arr1[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
	int arr2[] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
	int len = sizeof(arr1) / sizeof(arr1[0]);
	printf("交换前：\n");
	print(arr1, len);
	print(arr2, len);
	printf("交换后：\n");
	Exchange(arr1, arr2, len);
	system("pause");
	return 0;
}
void Exchange(int *arr1, int *arr2, int len){
	int temp = 0;
	for (int i = 0; i < len; i++){
		int *p = &arr1[i];
		int *q = &arr2[i];
		temp = *p;
		*p = *q;
		*q = temp;
	}
	print(arr1, len);
	print(arr2, len);
}
void print(int arr[], int len){
	for (int i = 0; i < len; i++){
		printf("%d ", arr[i]);
	}
	printf("\n");
}
