//Ayush Agarwal
//10800120130
#include <stdio.h>
int main()
{
    int a[100], n, i, j, position, swap;
    printf("how much elements you want to insert---");
    scanf("%d", &n);
    
    for (i = 0; i < n; i++)
    {
    printf("Enter the value of position %d---",i+1);
    scanf("%d", &a[i]);
    printf("\n");
    }
    for(i = 0; i < n - 1; i++)
    {
        position=i;
        for(j = i + 1; j < n; j++)
        {
            if(a[position] > a[j])
            position=j;
        }
        if(position != i)
        {
            swap=a[i];
            a[i]=a[position];
            a[position]=swap;
        }
    }
    printf("Sorted Array---: ");
    for(i = 0; i < n; i++)
    {
        printf("%d ", a[i]);
    }       
return 0;
}