1.리스트의 종류와 설명
-리스트의 종류

-연결리스트 : 크기에 대한 제약없어 유연하게 활용할 수 있지만 연결된 메모리가 아니기 때문에 데이터를 찾기 위해서는 모든 노드를 거쳐서 탐색해야 한다.
![list0](https://user-images.githubusercontent.com/55431033/68275831-04067e80-00b0-11ea-8f53-0d0d8e9dcd34.png)

-장점
필요할때마다 메모리를 동적으로 할당하기 때문에 메모리 효율적이다.
중간에 데이터를 삽입 또는 삭제 하더라도 다른 데이터에 영향을 주지 않아 효율적이다.
Ex> 'D'를 삭제하려면 'C'에서의 링크를 'E'로 변경만 하면 된다.
-단점
구현이 복잡하다.
중간의 데이터에 접근하기 위해서는 이전 노드를 모두 거쳐야만 접근할 수 있다.
Ex> 'D'에 접근하려면 'B', 'C'를 거쳐야만 한다.

-단일 연결 리스트
![list1](https://user-images.githubusercontent.com/55431033/68275836-0a94f600-00b0-11ea-8a66-db9d222ce763.png)
-코드 
typedef struct node
{
    struct node* next;
    void* data;
}Node;

-이중 연결 리스트
![list2](https://user-images.githubusercontent.com/55431033/68275858-0ff24080-00b0-11ea-93bb-98a2df76682b.png)
-코드
typedef struct node
{
    struct node* prev;
    struct node* next;
    void* data;
}Node;

-다중 연결 리스트
![list3](https://user-images.githubusercontent.com/55431033/68275926-1a143f00-00b0-11ea-860e-9d265b5aa859.png)
-코드
typedef struct node
{
    vector<struct node *> pointers;
    void* data;
}Node;

-원형 연결 리스트
![list4](https://user-images.githubusercontent.com/55431033/68275982-21d3e380-00b0-11ea-94c8-9c836e91ae4c.png)
리스트의 마지막 노드가 멀리있는 다른 노드(보통 첫번째 노드)를 가리키고 있는 형태이다.
 원형 이중 연결 리스트(circular doubly linked list)의 경우는 첫번째 노드의 prev는 마지막 노드를, 마지막 노드의 next는 첫번째 노드를 가리킨다.

  
  
