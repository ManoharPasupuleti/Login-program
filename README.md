# #include<stdio.h>
#include<string.h>
#include<stdlib.h>
void timer60(void)
{
int stat,id,j=60;
while(0<=j)
{
id = fork();
if(id==0)
{
sleep(1);
exit(0);
}
wait(&stat);
if(j<10)
printf("\r %d ",j);
else
printf("\r%d \b",j);
j--;
}
}
int main()
{
int opt,i=0,j=60,id,stat;
long int dob,mob;
char ch[30],name[40],pass1[15],pass2[20],pass[15],em[20],id1[20];
printf("WELCOME TO MANU LABS");
printf("\n1.SIGN UP\n 2.SIGN IN:");
scanf("%d",&opt);
switch(opt)
{
case 1:
{
printf("------ENTER YOUR DETAILS---------\n");
printf("\nENTER YOUR NAME:\t");
scanf("%s",name);
printf("\nEnter Your Date Of Birth:\t");
scanf("%ld",&dob);
printf("\nEnter Your Mobile number:\t");
scanf("%ld",&mob);
printf("\nEnter Your email:\t");
scanf("%s",em);
while(1)
	{	
printf("\nEnter Your Password:\t");
scanf("%s",pass);
printf("\nReEnter Password:\t");
scanf("%s",pass1);
printf("\n\n");
if(strcmp(pass,pass1)==0)
		{
		printf("SIGNUP SUCCESSFULLY\n\n\n");
		break;
		}
		else
		{
			printf("PLEASE ENTERCORRECTLY....\n\n ");}
		continue;
	}
}
case 2:
{
	do{
printf("ENTER ID:");
scanf("%s",id1);
printf("\nEnter Password:");
scanf("%s",pass2);
if((strcmp(em,id1)==0)&&(strcmp(pass1,pass2)==0))
	{
	printf("\t\t\t--------YOUR DETAILS---------\n\n");
	printf("\t\t\tHeLLO %s\n\n\n",name);
printf("\tYOUR NAME :\t\t%s\n\n",name);
printf("\tDATE OF BIRTH:\t\t%ld\n\n",dob);
printf("\tMOBILE NUMBER:\t\t%ld\n\n",mob);
printf("\t\t\tTHANK YOU...%s\n",name);
break;
	}
else
	{
	printf("\nENTER YOUR DETAILS CORRECTLY\n\n");
	i++;
	if(i==5){
	timer60();
	i=0;
	}
	
	}
}while(1);

}	
}
}
