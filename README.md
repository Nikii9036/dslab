#include<stdio.h>
#include<stdlib.h>
#define MAX 4
int stack[MAX],item,ch,top=-1,count=0,status=0;
void push(int stack[],int item)
{
if(top==(MAX-1))
printf("\n Stack Overflow");
else
{
stack[++top]=item;
status++;
}
}
int pop(int stack[])
{
int elem;
if(top==-1)
printf("\n Stack underflow");
else
{
elem=stack[top--];
status--;
printf("\n Poppoed element =%d",elem);
}
return elem;
}
void palindrome( int stack[])
{
int i,temp;
temp=status;
for(i=0;i<temp;i++)
{
if(stack[i]==pop(stack))
count++;
}
if(temp==count)
printf("\n stack contents are palindrome");
else
printf("\n stack contents are not pallindrome");
}
void display(int stack[])
{
int i;
printf("\n the stack contents are:");
if(top==-1)
printf("\t the stack isempty");
else
{
for(i=top;i>=0;i--)
printf("\n%d",stack[i]);
printf("\n");
}
}
int main()
{
do{
printf("\n--MAINMENU--\n");
printf("1.push 2.pop 3.palindrome 4.display 5.exit\n");
printf("enter your choice\t");
scanf("%d",&ch);
switch(ch)
{
case 1: printf("\n Enter the element:");
scanf("%d",&item);
push(stack,item);
break;
case 2: pop(stack);
break;
case 3: palindrome(stack);
break;
case 4: display(stack);
break;
default: exit(0);
break;
}
}while(1);
return(0);
}
