# Software Development

## Contents  
[**1. 데이터 입출력 구현**](#1-데이터-입출력-구현)  
[**2. 통합 구현**](#2-통합-구현)  
[**3. 제품 소프트웨어 패키징**](#3-제품-소프트웨어-패키징)  
[**4. 어플리케이션 테스트 관리**](#4-어플리케이션-테스트-관리)  
[**5. 인터페이스 구현**](#5-인터페이스-구현)  

----

## 1. 데이터 입출력 구현
1. 자료구조
	- 프로그램에서 사용하기 위한 자료를 저장하는 방법, 자료간의 관계 및 처리방법 연구분석
	- 종류
		- 선형 리스트 (Linear List)
			- 일정한 순서에 의해 나열된 자료 구조
			- 종류
				- 연속 리스트 (Contiguous List)
					- 연속된 기억장소에 저장되는 자료구조(배열)
					- 기억장소 이용효율 밀도 1 (좋음)
				- 연결 리스트 (Linked List)
					- 노드의 포인터 이용해 순서에 따라 서로 연결시킨 자료구조
					- 연속적으로 놓여있지 않아도 저장 가능
					- 노드 삽입 및 삭제 작업 용이
					- 기억 공간의 이용 효율 안 좋음, 접근 속도 느림
		- 스택 (Stack)
			- LIFO 방식의 자료구조
			- Overflow: 공간이 모두 채워져 있는 상태에서 데이터 삽입
			- Underflow: 더 이상 삭제할 데이터가 없는 상테에서 데이터 삭제
		- 큐 (Queue)
			- FIFO 방식의 자료구조
			- 포인터 구성
				- Front Pointer: 가장 먼저 삽입된 자료의 기억 공간 가리킴
				- Rear Pointer: 가장 마지막에 삽입된 자료의 기억 공간 가리킴
		- 그래프 (Graph)
			- 정점(Vertex)과 간선(Edge)로 구성된 자료구조
			- 방향성 유무에 따라 방향 그래프, 무방향 그래프로 구분
			- 트리(Tree)
				- 정점(Node)과 선분(Branch)을 이용해 사이클 이루지 않도록 구성한 그래프
				- 용어
					- Node: 하나의 기억 공간
					- Root Node: 트리의 맨 위에 있는 노드
					- Degree(차수): 각 노드에서 뻗어나온 가지의 수
					- Terminal Node(= Leaf Node): 자식이 없는 노드
					- Son Node: 어떤 노드에 연결된 다음 레벨의 노드
					- Parent Node: 어떤 노드에 연결된 이전 레벨의 노드
					- Brother Node(= Sibling): 동일한 부모를 갖는 노드들
					- 트리의 차수: 차수들 중 가장 많은 수
				- 운행법 (Traversal)
					- 트리를 구성하는 각 노드들을 찾아가는 방법
					- Preorder: Root -> Left -> Right
					- Inorder: Left -> Root -> Right
					- Postorder: Left -> Right -> Root

2. 정렬
	- 삽입 정렬 (Insertion Sort, O(n^2))
		- 모든 원소를 앞에서부터 정렬된 부분과 비교해 자신의 위치에 맞는 곳에 삽입  
		![image](https://user-images.githubusercontent.com/53277342/154679777-087513d1-aa63-4bce-8c25-03aebd2a5379.png)
		![image](https://user-images.githubusercontent.com/53277342/154679792-a137372a-169d-4a61-a89e-bbbf45344b33.png)
	- 셸 정렬 (Shell Sort, 평균 O(n^1.5), 최악 O(n^2))
		- 특정 매개변수 값의 길이를 갖는 부분 리스트 여러 개 생성 후 삽입 정렬  
		![image](https://user-images.githubusercontent.com/53277342/154680229-cf7b7c39-8923-43c0-a6c2-994eca1fbd70.png)
	- 선택 정렬 (Selection Sort, O(n^2))
		- 모든 원소 중 최소값을 찾아 맨 앞에 있는 값과 교체  
		![image](https://user-images.githubusercontent.com/53277342/154680874-de35524e-b172-42da-88d1-227f547a41ee.png)
	- 버블 정렬 (Bubble Sort, O(n^2))
		- 인접한 두 원소를 비교해 교차하면서 정렬  
		![image](https://user-images.githubusercontent.com/53277342/154681177-086e47f5-09b8-4576-8f2b-8fd253d8cbba.png)
	- 퀵 정렬 (Quick Sort, 평균 O(nlogn), 최악 O(n^2))
		- Pivot 기준으로 부분 리스트로 분할 후 정렬  
		![image](https://user-images.githubusercontent.com/53277342/154682153-c8ba59f4-a442-4386-895a-83336b783c80.png)
	- 힙 정렬 (Heap Sort, O(nlogn))
		- 전이진 트리(Complete Binary Tree)에서 자식 노드와 부모 노드 비교해 정렬  
		- ![image](https://user-images.githubusercontent.com/53277342/154683949-a7aa3caa-771c-44d2-8077-1bb728135c81.png)
	- 합병 정렬 (Merge Sort, O(nlogn))
		- 이미 정렬되어있는 두 개의 리스트를 하나로 합병 후 정렬  
		![image](https://user-images.githubusercontent.com/53277342/154684156-c3c69835-07c0-46b0-bf51-59faba607c5e.png)
	- 기수 정렬 (Radix Sort, O(dn))
		- 자릿수별로 정렬  
		![image](https://user-images.githubusercontent.com/53277342/154685160-29bf5d15-efd3-4947-b418-caf6d725d86c.png)





























