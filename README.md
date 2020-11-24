#include <stdio.h>
#include <stdlib.h>

struct n{
	int x;
	n * next;
};
typedef n node;

void print(node * h){
	while(h!=NULL){
		printf("%d ",h->x);
		h= h->next;
	}
}
void add(node *h, int x){
	while(h->next!=NULL){
		h = h->next;
	}
	h->next = (node*)malloc(sizeof(node));
	h->next->x = x; 
	h->next->next = NULL;
}
void clear(node *h,int a){
	
	scanf("%d",&a);
	if(h->x==a){
		node *temp=h;
		h=h->next;
		free(temp);
	}
	else{
		node *temp=h;
		node *temp2;
		while(temp->next->x!=a){
			temp=temp->next;
			
		}
	temp2=temp->next;
	temp->next=temp2->next;
	free(temp2);
	}
	
}
int main(){
	node * head;
	head=(node*)malloc(sizeof(node));
	head->next=NULL;
	head->x=500;
	int i=0;
	for(i=0;i<5;i++){
		add(head,i*10);
	}
	print(head);
	int s;
	printf("number to delete");
	clear(head,s);
	print(head);
}


