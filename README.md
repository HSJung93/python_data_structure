# python_data_structure
파이썬으로 자료구조를 구현한 코드 저장소입니다. 파이썬은 참 유용한 컴퓨터 언어입니다. 가벼운 프로젝트를 손쉽게 만들 때나 알고리즘을 구현하는 코딩테스트에서 참 유용합니다. 많은 부분이 유용한 만큼, 파이썬으로 자료구조에 대해서 공부할 때에는 와닿지 않는 면모들이 있었습니다. 그런 찜찜함을 없애기 위하여 파이썬으로 자료구조에 대하여 살펴보고 정리하고자 합니다.

## 자료구조
* 스토리지(HDD, SSD)는 가격이 저렴하고 용량이 크고 전원이 꺼져도 데이터가 저장된다.
* 메모리(DRAM)는 상대적으로 가격이 비싸고 용량이 적고 전원이 꺼지면 데이터가 사라진다. 대신 메모리가 스토리지보다 훨씬 빠르게 데이터를 저장하고 가져올 수 있다. 
* CPU는 스토리지와 메모리보다 빠르다. CPU가 스토리지에 비하여 너무 빠르다. 스토리지에 저장된 프로그램이나 파일을 메모리로 옮기고, 메모리에 있는 프로그램이나 파일을 CPU가 처리한다. 
* 이 메모리를 효율적으로 사용하고자 하는 것이 자료구조의 목적이다. 

## Linked List
### 링크드 리스트란?
* 연속적인 요소들이 포인터로 다시 연결되어 있다. 
* 마지막 요소는 널값(NULL, 파이썬에서는 None)을 가리킨다. 
* 프로그램 실행 도중에 사이즈가 늘어나거나 줄어들 수 있다.
* 포인터를 위한 추가적인 메모리가 필요하긴 하지만, 메모리 공간을 낭비하지 않는다. 
* 노드(node)라고 불리우는 자료를 가지고 있는 선형적인 자료 구조이다. 한 노드는 자료 값과 링크드 리스트의 다음 노드에 대한 참조(포인터)값을 가지고 있다. 
* 배열(Array)과 달리 런타임에 사이즈를 조정할 수 있는 동적인 자료 구조이다. 추가와 제거 작업이 효율적이고 구현하기 쉽다. 
* 배열(Array)과 달리 순차적으로 자료를 찾아야 하기 때문에 n번째 요소를 찾기 어렵다. 또한 순차적이기 때문에 역방향의 작업에 취약하다. 
* 값들이 메모리에 이웃해 있는 배열과는 달리, 임의로 넓게 퍼져있을 수 있다. 
* 일반적으로 배열은 컴파일 때에 크기가 고정되어 있고, 배열 메모리가 데이터 섹션(글로벌 배열)이나 스택 섹션(로컬 배열)에 할당되어 있는 자료구조이다. 이와 유사하게, 링크드 리스트는 크기가 고정되어 있지 않고 메모리가 힙 섹션(malloc()을 사용하는 등)에 할당된 자료구조이다. 배열은 스태틱 자료구조로, 링크드 리스트는 동적인 자료구조로 여겨진다.

### 구현할 작업들: 시간 복잡도
* insert: O(1)
* insert at end: O(n)
* insert at beginning: O(1)
* insert between: O(1)
* delete: O(1)
* search: O(n)
* indexing: O(n)

## Tree
### 트리란?
* 트리 또한 링크드 리스트와 같이 노드들이 연결된 자료의 구조이지만, 링크드 리스트와는 달리 한 노드에 여러 노드가 연결된 비선형적인 자료구조이다. 
* 트리의 **루트**는 부모가 없는 노드이며, 트리에는 단 하나의 루트 노드가 존재한다. 
* 엣지는 부모 노드로부터 자녀 노드로의 연결을 의미힌다.
* 자녀 노드가 없는 노드를 리프 노드라 부른다.
* 부모 노드를 공유하는 노드들은 시블링 노드라 부른다
* 정보를 찾기 쉽도록 만드는 자료구조이다.

### 이진트리란? 
* 트리의 각 노드가 0 혹은 3개의 자녀 노드만을 가지면 이진 트리라고 부른다.
* Full binary tree, Complete binary tree, Perfect binary Tree, Balanced binary tree, A degenerate(or pathological) tree.

### 트리 순회(Tree traversal)
* 비선형적인 자료 구조인 트리는 선형적인 자료 구조와는 달리 자료를 순회하는 방식이 하나가 아니다
1. Inorder: 좌 => 자료 => 우 
2. Preorder: 자료 => 좌 => 우
3. Postorder: 좌 => 우 => 자료

## Heap
### (이진) 힙이란?
* 이진 힙은 이진 트리의 일종이다. 
* 최소 힙이거나 최대 힙이다. 최소(최대)힙의 경우, 루트 노드의 키 값은 이진 힙의 모든 키 값 중 최소(최대) 값이라는 특징을 가진다. 이진 힙 안의 모든 부분 이진 트리들에 대해서도 재귀적으로 이 특징이 사실이다.  
* complete tree이기 때문에 배열에 저장하기 알맞다.
* 루트는 배열의 0번째가 아니라 1번째 값이다. 구현의 용이성을 위하여 0번째 인덱스는 생략한다. 
* 배열의 k번째 값을 키로 가지는 노드를 기준으로 왼쪽 자녀 노드의 키 값은 2*k번째에 위치하는 값이며, 오른쪽 자녀 노드의 키 값은 2*k+1번째 에 위치하는 값이다. 다시 말해 k번째 값을 키로 가지는 노드의 부모 노드의 키 값은 k//2번째 에 위치하는 값이다. 

### 사용처
* 힙소트: 이진힙을 사용하여 배열을 정렬하며 O(nlogn)의 수행시간을 가진다.
* 우선순위 큐: 우선순위 큐의 insert(), delete(), extractmax(), decreaseKey() 기능을 O(logn)의 시간복잡도로 구현할 때 사용된다. Binomial Heap이나 Fibonacci Heap으로 union을 효율적으로 구현할 수 있다.
* 그래프 알고리즘: 다익스트라 최소 경로나 Prim의 최소 spanning 트리 알고리즘에서 우선순위 큐가 사용된다.
* 그 외 배열에서 K번째로 큰 요소 구하기, 거의 정렬된 배열 정렬하기, k개의 정렬된 배열 합치기 등에 사용된다.

### 왜 이진 힙이 우선순위 큐보다 나은가?
* 배열에 구현되어 있기 때문에 참조의 지역성 측면에서 낫고, 작업이 캐쉬에 친화적이다.
* 같은 복잡도를 가지고 있지만, 이진 탐색 트리의 상수들이 더 높다. 
* 이진 힙은 O(n)에 구현할 수 있지만, 자가 균형 이진 탐색 트리는 O(nlogn)이 필요하다.
* 이진 힙은 포인터를 위한 추가적인 공간이 필요없다
* 이진 힙은 구현하기 쉽다.
* 피보나치 힙같은 경우 insert()와 decreasekey()를 더 효율적으로 구현할 수 있다.

