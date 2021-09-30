# DSA-MINI-PROJECT
#include <stdio.h>
#define M 10000

char a[M], b[M], c[M],d=0;
int k=M-1;
void fibbonacci(int x)
{
    if(x==0){
        printf("%d", 0);
        return;
    }
    else if(x==1){
        printf("%d", 1);
        return;
    }
    a[M-1]=1;
    b[M-1]=0;
    for(int i=2; i<=x; i++)
    {
        for(int i=M-1; i>=k; i--)
        {
            int y = a[i]+b[i]+d;
            c[i]=(y%10);
            d=y/10;
            if(i==k && d>0) 
            k--;
        }
        for(int i=M-1; i>=k; i--)
        {
            b[i]=a[i];
            a[i]=c[i];   
        }
    }
    for(int i=k; i<M; i++)
    {
        printf("%d", c[i]);
    }
    printf("\n");
}

int main()
{
    int n;
    scanf("%d", &n);
    fibbonacci(n);
    return 0;
}
