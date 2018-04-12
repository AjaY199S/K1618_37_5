#include<stdio.h>
#include<conio.h>
int main()
{
printf("Oprating System For Prority \n");
	
int n;
printf("\n\nEnter No. Of Student :- ");
scanf("%d",&n);

int i,Sname[n],gift[n],BT[n],CT[n],WT[n],TAT[n];
// Input Student buy Gift
	for(i=0;i<n;i++)
	{
			printf("\nStudent [%d]",i+1);
			Sname[i]=i+1;
        	printf("\nNo. Of Gifts :- ");
            scanf("%d",&gift[i]);
            BT[i]=gift[i];
	}

// for CT
int k,max=0,ind,sum=0;
for(k=0;k<n;k++)
{
	for(i=0;i<n;i++)
	{  
	
     	if(max<=gift[i])
	    {
		   max=gift[i];
		   ind = i;
		   
	    }  
   }
   sum=sum+gift[ind];
   CT[ind]=sum;
   TAT[ind] = sum;
   gift[ind] = -1;
   max=0;
}
   
//for WT And TAT,TAT = CT - AT
// AT[] = 0 ,CT=TAT
//WT = TAT - BT;
float A_WT,A_TAT,SWT=0,STAT=0;
for(i=0;i<n;i++)
{
	WT[i]=TAT[i]-BT[i];
}
for(i=0;i<n;i++)
{
	SWT = SWT + WT[i];
	STAT = STAT + TAT[i];
}
A_WT = SWT/n;
A_TAT = STAT/n;

int j;
	printf("\nStudent \tBT \tCT \tTAT \tWT ");
		for(j=0;j<n;j++)
	{
			printf("\n\nStudent[%d]\t%d \t%d \t%d \t%d",Sname[j],BT[j],CT[j],TAT[j],WT[j]);
	}
	
	printf("\n\nAverage Waiting Time(WT):-       %f",A_WT);
	printf("\nAverage Turn Around Time(TAT):- %f",A_TAT);

getch();
}
