# Hello-Word
The start of coding
#include <stdio.h>
int ZhongShu(int number [] ,int n)
{
    int i,p[100]={0};
    int count = 1, count1 = 1,index = 0;
    for(i = 0; i < n;i++ ) 
    {
        while(number[i]==number[i+1])
        {
            count++;
            i++;
        }
        if(count > count1) 
        {
            count1 = count;
            index = 0;
            p[index] = number[i];
        }
        else if(count == count1)
        {
            index++;
            p[index] = number[i];
        }
        count = 1;
    }
  if（index==n）
  {
     printf(“没有众数”);
  }
  else
  {
      for(i = 0; i <= index; i++) 
     {
        printf("众数为：%4d", p[i]);
      }
    return 0;
}

double Zhongweishu (int number [],int n)//求中位数
{
   if(n%2==0)
      return (number[n/2-1]+number[n/2])/2.0;
   else
     return number[n/2];
}



int main( )
{
    int n,i,j,number[100]={0},temp;
    double zhongweishu;
    printf("请问需要输入几位整数?\n");
    scanf("%d",&n);
    for(i=0;i<n;i++)
    {scanf("%d",&number[i]);}
    for(j=0;j<n;j++)
    {
       for(i=0;i<n-j;j++)
       {
          if(number[i]>number[i+1])
           {
              temp=number[i];
              number[i]=number[i+1];
              number[i+1]=temp;
           }
        }
    }
    zhongweishu=Zhongweishu(number,n);
    Zhongshu(number,n);
    printf(“中位数为：%f”,zhongweishu);
    return 0;
}
