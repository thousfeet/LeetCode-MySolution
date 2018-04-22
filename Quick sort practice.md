手写快排练习一下

```
//把小于支点的数扔到支点的左边，大于的扔到右边；返回支点位置 
int partition(int arr[], int L, int R)
{
	int pivot = arr[R]; //选择最后一个数字做支点 
	int j = L;
	for(int i = L; i <= R; i++)
	{
		if(arr[i] < pivot)
		{
			int tmp = arr[i];
			arr[i] = arr[j];
			arr[j] = tmp;
			j++;
		}
	}
	//交换最终j和支点位置数 
	int tmp = arr[R];
	arr[R] = arr[j];
	arr[j] = tmp;
	return j; 
}

void quicksort(int arr[], int L, int R) 
{
	if(L < R)
	{
		int M = partition(arr,L,R);
		quicksort(arr,L,M-1);
		quicksort(arr,M+1,R);
	}
}
```