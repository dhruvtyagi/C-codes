#include<stdio.h>
int greatest(long long int,long long int arr[1000]);
int main()
{
    long long int arr1[1000];
    long long int arr2[1000];
    long long int i,M,N,X,Y,cases,k,temp=0;
    scanf("%d",&cases);
    for(i=0;i<cases;i++)
    {
        scanf("%lld %lld %lld %lld",&M,&N,&X,&Y);
        for(k=0;k<N;k++)
        {
            arr2[k]=0;
            temp=N;
            temp=temp-k;
            M=M+k*Y;
            if(X*(temp)<=M)
                arr2[k]=temp;
        }
        arr1[i]=greatest(N,arr2);
    }
    for(i=0;i<cases;i++)
        printf("%d\n",arr1[i]);
    return 0;
}
int greatest(long long int N,long long int arr2[1000])
{
    long long int i;
    long long int max=arr2[0];
    for(i=0;i<N;i++)
    {
        if(arr2[i]>max)
            max=arr2[i];
    }
    return max;
}
