#include<stdio.h>
struct atm           //implementation of structure
{
    int loadcashatm;
    char customername[20];
    int accno;
    int checkaccno;
    int checkpinno;
    int pinno;
    int accblnc;
    int deno;
    int nors;
    int val;
};
int main()
{
    struct atm st[3];             //initilization
    int i,j;
    printf("LOAD CASH TO ATM");   //task 1 load cash
    for(i=0;i<3;i++)
    {
        printf("\n enter the denomination");
        scanf("%d",&st[i].deno);
        printf("\n enter the nors");
        scanf("%d",&st[i].nors);
    }
    printf("denomination\t number\t value\n");
    for(i=0;i<3;i++)
    {
         printf("\n");
        printf("%d \t  %d \t   %d ",st[i].deno,st[i].nors,st[i].deno*st[i].nors);
    }
      
     struct atm st1[6];      //taking one more array
     struct atm st3[6];  
     printf("\n   \t  MAINTAINING THE CUSTOMER DETAILS");
     for(i=0;i<3;i++)
     {
         printf("\n enter the account no");
         scanf("%d",&st1[i].accno);
         printf("\n account holder");
         scanf("%s", &st1[i].customername);
         printf("\n enter the pin number");
         scanf("%d",&st1[i].pinno);
         printf("\n enter the account balance");
         scanf("%d",&st1[i].accblnc);
     }
     printf("ACCNO\t ACCOUNT HOLDER \t PIN NUMBER\t ACCOUNT BALANCE");
     for(i=0;i<3;i++)
     {
         printf("\n");
         printf("%d \t %s \t  %d  \t  %d  \t",st1[i].accno,st1[i].customername,st1[i].pinno,st1[i].accblnc);
     }
     
     printf("\n      HANDLING ATM PROCESS");
     int c,val=0;
     printf("\n    THE ACCOUNT NUMBER YOU ENTERED IS VALID");
     printf("\n 1.CHECK BALANCE \n 2. WITHDRAW MONEY \n 3.TRANSFER MONEY \n 4.CHECK ATM BALANCE");
     printf("\n enter your choice");
     scanf("%d",&c);
     struct atm st2[3];
     int n,max,min,num,money;
     printf("\n enter the number of accounts to check");
     scanf("%d",&n);
     switch(c)
     {
         case 1:
     for(i=0;i<n;i++)
     {
         printf("\n enter the account number");
         scanf("%d",&st2[i].checkaccno);
         printf("\n enter the pin no");
         scanf("%d",&st2[i].pinno);
     }
     for(i=0;i<6;i++)
     {
     if(st1[i].accno==st2[i].checkaccno&&st[i].pinno==st2[i].checkpinno)
     {
         val++;
     }
     }
     for(i=0;i<=val;i++)
     {
         printf("YOURS BALANCE IS :%d",st1[i].accblnc);
     }
     break;
      case 2:
      max=10000;
      min=100;
      printf("\n enter your pin number");
      scanf("%d",&num);
      for(i=0;i<3;i++)
      {
          if(num==st1[i].pinno)
          {
          printf("\n it is valid pin");
          }
          else
          {
              printf("\n it is not valid");
          }
      }
      printf("\n enter the money to be withdrawn ");
      scanf("%d",&money);
      for(i=0;i<3;i++)
      {
      if(money>st1[i].accblnc)
      {
          printf("\n INSUFFICIENT BALANCE");
      }
      else
      {
          printf("\n COLLECT YOUR MONEY");
      }
      break;
      }
      case 4:
      printf("\n ATM BLALNCE");
      for(i=0;i<3;i++)
      {
          printf("\n enter the denomination");
          scanf("%d",&st3[i].deno);
          printf("\n enter the no");
          scanf("%d",&st3[i].nors);
      }
      int sum=0;
      printf("DENOMINATION\t NUMBER\t VALUE");
      for(i=0;i<3;i++)
      {
          printf("\n");
          printf("%d\t %d \t %d\t",st3[i].deno,st3[i].nors,st3[i].deno*st3[i].nors);
          sum=sum+st[i].deno*st3[i].nors;
          printf("\n");
          printf("TOTAL AMOUNT AVAILABLE IN THE ATM= %d",sum);
      }
     
      }
}
