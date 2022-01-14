#include <stdio.h>  
#include<stdlib.h>
void merge_All(int a[100], int beg, int mid, int end)    
{    
    int i, j, k;  
    int n1 = mid - beg + 1;    
    int n2 = end - mid;    
      
    int LeftArray[n1], RightArray[n2]; 
    for (int i = 0; i < n1; i++)    
    LeftArray[i] = a[beg + i];    
    for (int j = 0; j < n2; j++)    
    RightArray[j] = a[mid + 1 + j];    
      
    i = 0; 
    j = 0; 
    k = beg;
      
    while (i < n1 && j < n2)    
    {    
        if(LeftArray[i] <= RightArray[j])    
        {    
            a[k] = LeftArray[i];    
            i++;    
        }    
        else    
        {    
            a[k] = RightArray[j];    
            j++;    
        }    
        k++;    
    }    
    while (i<n1)    
    {    
        a[k] = LeftArray[i];    
        i++;    
        k++;    
    }    
      
    while (j<n2)    
    {    
        a[k] = RightArray[j];    
        j++;    
        k++;    
    }    
}    
  
void merge_Sort(int a[], int beg, int end)  
{  
    if (beg < end)   
    {  
        int mid = (beg + end) / 2;  
        
        merge_Sort(a, beg, mid);  
        merge_Sort(a, mid + 1, end);  
        merge_All(a, beg, mid, end);  
    }  
}  
   
void printArray(int a[], int n)  
{  
    int i;  
    for (i = 0; i < n; i++)  
        printf("%d ", a[i]);  
    printf("\n");  
}  
  
int main()  
{  
    int a[100],n;
    printf("how many elements you want to store in your linked list\n");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
   {
      printf("please enter your data No-%d ",i+1);
      scanf("%d",&a[i]);
      printf("\n");  
   }  
    printf("Before sorting array elements are - \n");  
    printArray(a, n);  
    merge_Sort(a, 0, n - 1);  
    printf("After sorting array elements are - \n");  
    printArray(a, n);  
    return 0;  
}  