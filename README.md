# delete-any-node-from-LinkedList-in-C

#include<stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node* next;
    
};

void delete(struct node *head , int position){
    struct node *temp ;
    temp=head;
    int i;
    if(position==1){
        head=head->next;
        free(temp);
        temp=head;
        
        while(temp!=NULL){
            printf("%d",temp->data);
            temp=temp->next;
            
        }
    }
    
    else{
        for(i=1;i<position-1;i++){
            temp=temp->next;

        }
        temp->next=temp->next->next;
        
        
    
     while(head!=NULL){
            printf("%d",head->data);
            head=head->next;
            
        }
    }


}




int main()
{
    int pos=0;
    printf("enter position=");
    scanf("%d",&pos);
    struct node* head, *second , *third , *fourth , *fifth , *sixth;
    head= (struct node *)malloc(sizeof(struct  node));
    second= (struct node *)malloc(sizeof(struct  node));
    third= (struct node *)malloc(sizeof(struct  node));
    fourth= (struct node *)malloc(sizeof(struct  node));
    fifth= (struct node *)malloc(sizeof(struct  node));
    sixth= (struct node *)malloc(sizeof(struct  node));
    //seven= (struct node *)malloc(sizeof(struct  node));
    
    
    head->data=1;
    head->next=second;
    
    second->data=2;
    second->next=third;
    
    third->data=3;
    third->next=fourth;
    
    fourth->data=4;
    fourth->next=fifth;
    
    fifth->data=5;
    fifth->next=sixth;
    
    sixth->data=6;
    sixth->next=NULL;
    
    delete(head,pos);
    
 
    
    return 0;
}
