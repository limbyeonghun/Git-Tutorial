1.리스트의 종류와 설명

-리스트의 종류

1) 연결리스트 : 크기에 대한 제약없어 유연하게 활용할 수 있지만 연결된 메모리가 아니기 때문에 데이터를 찾기 위해서는 모든 노드를 거쳐서 탐색해야 한다.
![list0](https://user-images.githubusercontent.com/55431033/68275831-04067e80-00b0-11ea-8f53-0d0d8e9dcd34.png)

-장점
필요할때마다 메모리를 동적으로 할당하기 때문에 메모리 효율적이다.
중간에 데이터를 삽입 또는 삭제 하더라도 다른 데이터에 영향을 주지 않아 효율적이다.
Ex> 'D'를 삭제하려면 'C'에서의 링크를 'E'로 변경만 하면 된다.

-단점
구현이 복잡하다.
중간의 데이터에 접근하기 위해서는 이전 노드를 모두 거쳐야만 접근할 수 있다.
Ex> 'D'에 접근하려면 'B', 'C'를 거쳐야만 한다.

2) 단일 연결 리스트
![list1](https://user-images.githubusercontent.com/55431033/68275836-0a94f600-00b0-11ea-8a66-db9d222ce763.png)
-코드 
typedef struct node
{
    struct node* next;
    void* data;
}Node;

3) 이중 연결 리스트
![list2](https://user-images.githubusercontent.com/55431033/68275858-0ff24080-00b0-11ea-93bb-98a2df76682b.png)
-코드
typedef struct node
{
    struct node* prev;
    struct node* next;
    void* data;
}Node;

4) 다중 연결 리스트
![list3](https://user-images.githubusercontent.com/55431033/68275926-1a143f00-00b0-11ea-860e-9d265b5aa859.png)
-코드
typedef struct node
{
    vector<struct node *> pointers;
    void* data;
}Node;

5) 원형 연결 리스트
![list4](https://user-images.githubusercontent.com/55431033/68275982-21d3e380-00b0-11ea-94c8-9c836e91ae4c.png)
리스트의 마지막 노드가 멀리있는 다른 노드(보통 첫번째 노드)를 가리키고 있는 형태이다.
 원형 이중 연결 리스트(circular doubly linked list)의 경우는 첫번째 노드의 prev는 마지막 노드를, 마지막 노드의 next는 첫번째 노드를 가리킨다.
 
 
 
2.트리의 종류와 설명
 
- 트리의종류

1) 완전 이진 트리
완전 이진 트리는 왼쪽자식노드부터 채워지며 마지막 레벨을 제외하고는 모든 자식노드가 채워져있는 트리이다
 
 ![tree0](https://user-images.githubusercontent.com/55431033/68277695-146c2880-00b3-11ea-87d3-a0d2a273d9bb.png)
 
왼쪽부터 채워져있고 마지막 레벨을 제외하곤 모두 자식노드가 있으므로 완전 이진 트리이다.
 
 2) 포화 이진 트리
포화 이진 트리는 모든 노드가 0개 혹은 2개의 자식노드를 가지며 모든 리프노드가 똑같은 레벨에 있는 경우의 트리이다

![tree1](https://user-images.githubusercontent.com/55431033/68277696-1504bf00-00b3-11ea-821f-154f9b68ae55.jpg)

3) 정 이진 트리
정 이진 트리는 모든 노드가 0개 혹은 2개의 자식노드를 가지는 트리를 말한다. 포화 이진 트리의 하위종류이다.

![tree2](https://user-images.githubusercontent.com/55431033/68277698-1635ec00-00b3-11ea-8596-dc7652157cea.png)

4) 편향 이진 트리
편향 이진 트리는 말 그대로 노드들이 전부 한 방향으로 편향된 트리이다.

![tree3](https://user-images.githubusercontent.com/55431033/68277704-17ffaf80-00b3-11ea-8675-3967fe77ae49.png)

5) 이진 탐색 트리
이진 탐색 트리는 이진트리의 종류이긴 하지만 굉장히 중요하기 때문에 따로 빼서 정리하기로 한다.
이진트리이지만 왼쪽 자식노드가 루트노드보다 작고, 오른쪽 자식노드가 루트노드보다 큰 트리를 이진 탐색 트리라고 한다.

![tree4](https://user-images.githubusercontent.com/55431033/68277706-1930dc80-00b3-11ea-8b3b-16d8d8b92657.jpg)

이렇게 각각의 노드들이 조건을 만족하는 것을 알 수 있다.
여기서 중위순회(Inorder Traveral)을 적용하면 오름차순 정렬이 된다. 하지만 전위순회/후위순회는 딱히 의미가 없다.
이진 탐색 트리의 종류 중에는 AVL 트리가 있는데 이는 편향 이진 트리를 이진 탐색 트리로 순회했을 때 끝까지 탐색하는 비효율성을 거쳐서
편향 이진 탐색 트리로 하여금 균형을 맞춘 트리를 말한다. 그렇지만 균형을 맞추는 작업 자체가 복잡하기 때문에 나중에 따로 정리하기로 한다




 


  
  
