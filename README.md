#include <stdio.h>
#define max 5
void insert_circular_queue();
void delete_circular_queue();
void circular_queue_display();
int q[5],a;
int rear= -1,front=-1;
int main()
{
int ch;
do
{
printf("\nenter the choice\n");
scanf("%d",&ch);
 switch (ch) 
 { 
case 1:insert_circular_queue();
break;
case 2:delete_circular_queue();
break;
 	case 3:circular_queue_display();
 	case 4:exit(0);
default:
 	printf("invalid choice");
}  
}  
while(1);
}
void insert_circular_queue()
{
int data;
if(((front==0)&&(rear==max-1))||(rear+1==front))
printf("the circular queue is overflow");
else
{
printf("\nenter the data\n");
scanf("%d",&data);
if(rear==-1)
{
rear=0;
front=0;
}
else if (rear==max-1)
rear=0;
else
rear++;
q[rear]=data;
}
}
void delete_circular_queue()
{
	a=q[front];
if(front==-1)
printf("circular queue is underflow");
else
{
printf(" the delete data is %d",a);
if(front==rear)
front=-1,rear=-1;
else if(front==max-1)
front=0;
else
{
front++;
}
}
}
void circular_queue_display()
		{
		int i,j;
			if (front==-1&&rear==-1)
			printf("\nCircular queue is underflow");
			if(front>rear)
			for(i=front;i<max;i++)
			for(j=0;j<=rear;j++)
			printf("\n%d",q[j]);
			printf("\nthe circular queue data are:");
			for(i=front;i<=rear;i++)
			printf("%d\n",q[i]);
				}
