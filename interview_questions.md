**1. Added node in sorted list**
```

typedef struct node {
	struct node *next;
	int data;
} node_t;


node_t *add_node(node_t *head, int data)
{
	node_t *new = NULL;
	node_t *ptr = NULL;

	new = malloc(sizeof *node);
	if (new == NULL) {
		perror("malloc failed");
		return NULL;
	}

	new->next = NULL;
	new->data = data;

	if (head == NULL) {
		head = new;
		return head;
	}


	ptr = head;

	while(ptr != NULL) {
		if (new->data > ptr->data) {
			ptr->next = new;
		} else if () {
			
		}

	}

}
```

**Single Linked List add the node & insert the node in 1st, middle, last and position based sample programs** <br>

```
#include<stdio.h>
#include<stdlib.h>
struct singly{
	int data;
	struct singly *next;
}*head = NULL;

void create(value)
{
	struct singly *new=NULL;
	struct singly *temp=NULL;
	if(head==NULL)
	{
		head =(struct singly *)malloc (sizeof(struct singly));
		if(head==NULL)
		{
			printf("memory allocation failed!");
			return;
		}
		else
		{
			head->data =value;
			head->next =NULL;
		}
	}
	else
	{
		temp =head;
		while(temp->next!=NULL)
		{
			temp =temp->next;
		}
		new =(struct singly *)malloc (sizeof(struct singly));
		if(new==NULL)
		{
			printf("memory allocation failed!");
			return;
		}
		else
		{
			new->data=value;
			new->next=NULL;

			temp->next=new;
		}
	}
}
void insert_first(int value)
{

	struct singly *new=NULL;
	new =(struct singly *)malloc (sizeof(struct singly));
	new->data =value;
	new->next =head;
	head =new;
}
void insert_last(int value)
{

	struct singly *temp=NULL;
	struct singly *new=NULL;
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
	}
	new =(struct singly *)malloc (sizeof(struct singly));
	new->data =value;
	new->next =NULL;
	temp->next =new;
}
void insert_middle(int value)
{

	struct singly *temp=NULL;
	struct singly *new=NULL;
	int count =0,posi=0;
	temp =head;
	while(temp->next!=NULL)
	{
		count++;
		temp =temp->next;
	}
	count=count/2;
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
		posi++;
		if(count==posi)
		{

			new =(struct singly *)malloc (sizeof(struct singly));
			new->data =value;
			new->next =temp->next;
			temp->next =new;
		}
	}
}
void insert_position(int value)
{
 struct singly *temp=NULL;
	struct singly *new=NULL;
	int count =0,posi=0;
	printf("enter the position");
	scanf("%d",&posi);
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
		count++;
		if(count==posi)
		{

			new =(struct singly *)malloc (sizeof(struct singly));
			new->data =value;
			new->next =temp->next;
			temp->next =new;
		}
	}
}
void display()
{
	struct singly *temp =NULL;
	temp=head;
	while(temp!=NULL)
	{
		printf("%d->",temp->data);
		temp=temp->next;

	}
	printf("NULL");
}

void main()
{
	create(10);
	create(20);
	create(30);
	insert_first(100);
	insert_last(300);
	insert_middle(200);
	insert_position(400);
	display();
}

```

**Find the duplicate in Single linked list** <br>
```
#include<stdio.h>
#include<stdlib.h>
struct get{
	int data;
	struct get *next;
};
struct get *h=NULL;
struct get *head1=NULL;
void create (int value)
{
	struct get *temp = NULL;
	struct get *new = NULL;

	if (h==NULL)
	{
		h = (struct get *)malloc (sizeof(struct get));
		if (h==NULL)
		{
			printf ("memory allocation failed");
			return;
		}
		else
		{
			h->data = value;
			h->next = NULL;
		}
	}
	else
	{
		temp = h;
		while(temp->next!=NULL)
		{
			temp =temp->next ;
		}
		new = (struct get *)malloc (sizeof(struct get));
		new->data = value;
		new->next = NULL;
		temp->next = new;
	}

}
void sorting ()
{

	struct get *temp = NULL;
	struct get *new = NULL;
	int s;
	temp =h;
	while (temp!=NULL)
	{
		new = temp->next;
		while (new!=NULL)
		{
			if (temp->data > new->data)
			{
				s = temp->data;
				temp->data=new->data;
				new->data=s;
			}
			new=new->next;
		}
		temp= temp->next;
	}
}
void duplicate ()
{

	struct get *temp = NULL;
	struct get *new = NULL;
	struct get *s = NULL;
	struct get *b = NULL;
	int count =0;
	temp =h;
	//new = temp->next;
	while (temp!=NULL)
	{
		new = temp->next;
		while (new!=NULL)
		{
			if (temp->data ==  new->data)
			{
//				printf ("%d %d",temp->data,new->data);
				s = new->next;
				free (new);
				new = s;
//				printf (" %d ",temp->data);

			}
			else
			{
				new= new->next;
			}
		}
		temp=temp->next;
	}
}
void display ()
{

	struct get *temp = NULL;
	int count =0,pos=0;
	temp = h;
	while(temp!=NULL)
	{
		printf("%d->",temp->data);

		temp = temp->next;
	}
	printf("NULL");
}
void main()
{
	create(60);
	create(20);
	create(30);
	create(70);
	create(50);
	create(10);
	sorting ();
	duplicate();
	display();
}
```
**2. Reversing doubly linked list**
```
typedef struct node {
	struct node *next;
	int data;
} node_t;

int reverse(node_t *head)
{
	node_t *ptr = NULL;

	if (head == NULL) {
		return -1;
	}

	ptr = head;	

	while(ptr != NULL) {
		if (ptr->next != NULL) {
			next = ptr->next;
			prev = ptr->prev;
			ptr->next = prev;
			ptr->prev = next;
		}
		ptr = next
	}
}
```
**3. What is dangling pointer?** <br>
A pointer pointing to a memory location that has been deleted (or freed) is called dangling pointer.

```

int a;
static int b;

int main()
{
	static int c;
	char *ptr = (char *)malloc(10);

	free(ptr);

	ptr ///
}
```

what if dest mac is not match in switch and router ?<br>
fragmentation in ip stack ?<br>
what if frame exceeds the mtu size ?<br>
	if fragmentation enable, the frame get fragment<br>
max port no ?<br>
can we set own client port no ?<br>
what listen will do ?<br>
	monitor incomming req and create passive sockets<br>
How global values are acceseddd in parent and child ?<br>
how mutex values in acccess by two process (bcz two procs are not communicate) ?<br>
is static varible with same name is cause compilation error ?<br>
when global variables get resolve ?<br>
need of volatile with compiler flag O0 ?<br>
	need to remove optimization for specific variable<br>
memory barrier in kernel<br>
net filters<br>
TCP handshake<br>
packet lifecycle<br>
how stp select root node ? based on mac addr<br>
diff snmp walk and bulk walk<br>
trap and alram<br>
need of makefile<br>


set 0 to diagnal elements in multi-dimension matrix
```
int nullit(int arr[][], size_t size)
{
	int i = 0;
	int j = 0;
	
	for(i = 0; i < size; i++) {
		for (j = 0; j < size; j++) {
			if ((i == j) || ((i == 0) && (j == size -1)) || ((i == size - 1) && (j = 0)) {
				arr[i][j] = 0;
			}
		}
	}
}

will work only for 3x3
```

remove node only with node pointer. (no reference to head pointer)
memory segment

List program
```
take ll reverse 

a b c d e f g h
a h c f e d g b

___ func()

int func (struct node *list)
{
    int i = 0, j = 0;
    struct node *current = NULL;
    strcu node *end = NULL;
    
    if (list == NULL) {
        return -1; //null head
    }

    current = list;
  
    while(current != NULL) {
        current = current->next;
    }
   
    end = current; //points end node
    
    current = list; //resetting first node
	
    while (current != NULL) {
        if (current->next != NULL) {
            new = end;
            end->prev->next = current->next;
			if (end->prev->prev != NULL) {
				end = end->prev->prev;
			}	
            new->next = current->next->next;
            new->prev = current;
            current->next = new;
            
            if (current->next->next != NULL) {
				current = current->next->next;
			}
        }
    }
	
	return 0;
}
```
What are all the restrictions for writing the kernel modules?<br>
	could not use printf, malloc will use kprintf and kmalloc<br>
How host know its IP?<br>
How router know its own packets becuase it does not have routing table for that.<br>
how vlagrind reports memory leak and how it know?<br>
how malloc works and its memory header?<br>
What symbol table consists?<br>
what is ELF and what it consists?<br>
What is best data-structure to maintain routing table?<br>
Type of IPC<br>
Diff of Socket and Shared Memory<br>
Ethernet field<br>
Swap bit from x to y<br>
```
num = 1011101110111011
ans   1011111111111011

mask = 111111111111111
a = 111111111111000
b = 111110000000000
mask = a^b = 0000001111111000
ans = num | mask
ans   1011111111111011
```
Remove duplicates in a list: 
- dont use loop
- can use merge sort to remove dups (not suitable for the list does not require sorting)
- can use hashing
```
1-->2-->2-->3
1-->2-->3

1-->1-->2-->3-->2
1-->2-->3

struct node {
    struct node *next;
    int data;
};

int remove_dups(struct node *list)
{
    int retavl = -1;
    struct node *curr = NULL;
    struct node *next = NULL;
    struct node *tmp = NULL;
    
    do {
        if (list == NULL) {
            fprintf(stderr, "list is null\n");
            retval = -1;
            break; 
        }

        while(curr != NULL) {
            curr = list;
            next = curr->next;

            while(next != NULL) {
                if (curr->data == next->data) {
                    //remove duplicate node
                    curr->next = next->next;
                    free(
                }
            }
        }

        if (curr->next == NULL) {
            /* list has only one element. and no duplicates. */
            fprintf(stderr, "only one element\n");
            retval = 0;
            break; 
        } else {
            next =

        }
    } while(0);

    return retval;
}
```
Where the shared memory will create memory?<br>
--user space memory in file system as a file.<br>
How to create the new process?<br>
--- fork and exec<br>
Diff process and threads.<br>
Ret val of fork()<br>
How to insert a new module in kernel?<br>
--- insmod and modprobe<br>
What are the fields will change in a packet from Router to switch?<br>
---Source and dest MAC, Checksum and TTL.<br>
Program to return array of structure and how to chk the return value?<br>
Output of below code 
```
int *ptr=NULL;
ptr=ptr+1;
printf("%d\n",ptr);
```
Ahow to access the a[2][2] in pointer method in below array?<br>
```
123
456
789
```
Memory layouts<br>
Use of static variables<br>
Where the memory is allocated for Extern variable<br>
Type of sockets?<br>
---Sytream(TCP) and Datagram(UDP) and also we have Raw socket (ICMP)<br>
What is deadlock<br>

Output of below code:<br>
```
main()
{
    const int q = 5;
    int const* p = &q; 

    *p = 7;
    printf ("%d", *p);        
    
    return 0;
 }
```
Program for below matric<br>
```
1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
```
Memory pattern of little endian and big endian<br>
List to check palindrom<br>
```

NULL <-- 1 <--> 0 <--> 1 <--> 0 <--> 1 --> NULL

2 1 2 2 1
    1 2 3


fun(struct node *list)
{
	strcut node *tmp = NULL;
	strcut node *last = NULL;

	if (list == NULL) {
		return -1; //empty list
	}

	tmp = list;
	while(tmp->next != NULL) {
		tmp = tmp->next;
	}

	last = tmp;
	tmp = list;

	while(tmp != NULL) {
		if (tmp->data != last->data) {
			return -1; // list is not a palindrome
		}
		tmp = tmp->next;
		last = last->prev;
	}

	return 0;
}
```
Consequtive dynamic allocation for multi-dimension array
```
struct node {
	struct node *next;
	struct node *prev;
	int data;
};

int main()
{
	//char a[2][5];

	char **b = NULL;
	int r = 2; c = 5;

	b = (char **)malloc(size);
	if (b == NULL) {
		perror("malloc failed");
		return -1;
	}

	while(i < r) {
		b[i] = malloc(c * sizeof (**b));
		if (b[i] == NULL) {
			perror("malloc failed");
			return -1;
		}
		i++;
	}
}
```
Ethernet frame fields<br>
Packet travel between  ```host -- switch --- host``` and ```host --- router --- host```.

**How does free() know the size of memory to be deallocated?**

When memory allocation is done, the actual heap space allocated is one word larger than the requested memory.<br> 
The extra word is used to store the size of the allocation and is later used by free( ).

**1.what is the difference b/w structure and union?.
  Ans: Struct-> The size of structure is equal or greater than sum of size of its members.
 union-size of union is equal to the size of largetest member.
 
 2.what are the derived data types?.
 
 Ans:Pointers, arrays, structures and unions are derived data types.
 
 3.How we can find out circular linked list or not?.
 4.Explain memory layout for c?.
 5.what is the size of below structure?.
   struct str{
     int a;
	 char b;
	 int c;
	 char d;
	 int e;
   }
   
  6.In structure pading how to reduce the memory size?
  7.if free(90)-random number---> what happend?
  8.what is the use of stp?
  9.what is the use of vlan? and explain?
  10.what is the array?**
  
