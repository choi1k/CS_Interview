# Linked List

### 연결리스트
\
  <img width="70%" src="https://user-images.githubusercontent.com/75103526/208240526-2c3f9bd0-870f-4f45-8101-f2d62b5e3cee.png"/>
  
  * 연결리스트란?
  
    연결리스트는 각 노드가 데이터와 포인터를 가지고 한 줄로 연결된 방식으로 데이터를 저장하는 자료구조임
  
    각 노드는 다음 노드를 가리키는 포인터를 포함
  
    포인터는 다음 노드의 주소 값을 가지고 있음
    
  * 시간 복잡도
   
    * 삽입
    
          리스트 가장 앞/뒤에 삽입하는 경우 : O(1)
          리스트 중간에 삽입하는 겨우 : O(n)
          
    * 삭제
    
           리스트 가장 앞/뒤에 삭제하는 경우 : O(1)
           리스트 중간에 삭제하는 경우 : O(n)
    
    * 탐색
           
           O(n)
           
  * 장점
   
    삽입/삭제 용이 : 포인터가 가리키고 있는 노드 변경만으로 삽입과 삭제 가능
     
    동적 크기 : 새로운 원소 추가 시 동적으로 크기가 변경됨
     
    불연속적 메모리 할당 : 중간 데이터 삭제 시 배열과 달리 빈공간 없이 데이터 저장 가능
     
    메모리 재사용
     
  * 단점
   
    인덱스 활용 불가능 : 탐색 시 인덱스가 아닌 반복자를 활용하여 탐색을 진행하기 때문에 속도가 느림
    
    포인터를 위한 별도의 저장 공간 필요 : 포인터를 저장하기 위해 별도의 저장 공간이 요구됨
    
    
  * 사용하는 경우 
   
    크기가 정해져 있지 않을 때
     
    삽입/삭제가 빈번히 발생할 때
     
    검색이 자주 발생하지 않을 때
    
# Array vs ArrayList vs LinkedList
    
* Array는 index를 활용해 빠른 탐색이 가능
    
* LinkedList는 포인터를 활용해 빠른 삽입/삭제가 가능
    
* ArrayList는 빠른 탐색이 가능하지만 삽입/삭제가 느림

### Array

배열은 메모리 공간에 할당할 사이즈를 미리 정해놓고 사용하는 자료구조이므로 그 사이즈를 알 수 없거나,
저장할 데이터가 계속해서 증가하는 경우 적합하지 않음

또한, 삽입/삭제 시 모든 자료를 한 칸씩 미루거나 당겨야 하기 때문에 매우 비효율적임

하지만 index를 활용해 데이터의 위치를 빠르게 알 수 있어 검색이 자주 발생하는 경우 적합함

### List

List는 배열과 달리 메모리 공간에 할당할 사이즈를 미리 정해주지 않아도 됨

삽입/삭제 시 원소가 가리키는 주소만 변경해주면 됨

단, 다른 요소의 주소를 저장하기 위한 추가적 메모리 공간을 필요로함

### LinkedList

포인터를 활용해 삽입/삭제 작업이 빠르게 진행됨

하지만 index가 없기 때문에 배열, List와 달리 순차적 탐색이 발생해 검색에는 비효율적임

# Heap

### 힙

* 힙이란?

  완전 이진 트리의 일종으로 우선순위 큐를 위해 만들어진 자료구조임

  여러 개의 값 중 최대값이나 최솟값을 빠르게 찾아낼 때 
  
  힙 트리는 중복된 값을 허용함 (이진 탐색 트리에서는 중복된 값을 허용하지 않음)
  
  느슨한 정렬 상태(반정렬 상태) 유지

* 시간 복잡도
   
    * 삽입
    
           O(logN) : O(n)이지만 heapify 과정이 O(logN)이기 때문
          
    * 삭제
    
           O(logN) : O(n)이지만 heapify 과정이 O(logN)이기 때문
    
    * 힙 생성
           
           O(NlogN) : heapify 과정이 N번 반복됨
* 힙 구현  

  힙을 저장하는 표준적 자료구조는 배열임
  
  구현을 보다 용이하게 하기 위해 배열의 첫 번째 인덱스 0은 사용되지 않음
  
  특정 위치의 노드 번호는 새로운 노드가 추가되어도 번호가 상항 동일함
    
     * 루트 노드의 오른쪽 노드의 번호는 항상 3임
  
* 부모 노드와 자식노드 관계

      왼쪽 자식의 인덱스 = (부모의 인덱스) * 2
      
      오른쪽 자식의 인덱스 = (부모의 인덱스) * 2 + 1
      
      부모의 인덱스 = (자식의 인덱스) / 2

* 힙 삽입

  1. 새로운 요소는 힙의 마지막 노드에 이어 삽입됨
  
  2. 새로운 노드를 부모 노드와 교환하며 힙의 성질을 만족시킴
  
* 힙 삭제

  1. 최대 힙, 최소 힙 모두 루트 노드를 삭제함
    
      (최대 힙에서 삭제 = 최대값 삭제, 최소 힙에서 삭제 = 최솟값 삭제)
    
  2. 말단 노드를 루트 노드로 가져옴
  
  3. 새로운 루트 노드를 자식 노드와 교환하며 힙의 성질을 만족시킴

* 최대 힙(max heap)
  
  부모 노드의 키 값이 자식 노드의 키 값보다 크거나 같은 완전 이진 트리
  
  key(부모 노드) >= key(자식 노드)
  
  <img width="40%" src="https://user-images.githubusercontent.com/75103526/208243922-44cc3f4d-7896-4685-99be-f2bd515e919e.png"/>
  
* 최소 힙(min heap)
  
  부모 노드의 키 값이 자식 노드의 키 값보다 작거나 같은 완전 이진트리
  
  key(부모 노드) <= key(자식 노드)

  <img width="40%" src="https://user-images.githubusercontent.com/75103526/208243947-1e8f6046-fbc8-4206-b66a-2eb69374214d.png"/>
  
# Trie

### 트라이

* 트라이란?

  트라이는 문자열을 저장하고 효율적으로 탐색하기 위한 트리 형태의 자료구조임
  
  트리의 루트부터 자식을 따라가면서 생성된 문자열들이 트라이 자료구조에 저장되어 있음
  
  <img width="45%" src="https://user-images.githubusercontent.com/75103526/208288980-846e843b-c544-48b3-a063-80fb23893089.png"/>
  
* 사용하는 경우

  문자열 검색
  
      이진탐색트리를 활용해 정수를 검색할 경우 시간 복잡도는 O(logN)이 됨
      
      이를 문자열에 적용하면 문자열의 길이가 M인 경우, 시간 복잡도는 O(M * longN)이 됨
      
      이때, 트라이를 활용하면 O(M)으로 문자열 검색이 가능함
  
# B Tree & B+ Tree

### B Tree

* B Tree란?

  B Tree는 일반적으로 B- Tree를 의미하며, Balanced Tree로 균형을 유지하는 트리임 \
  따라서 최악의 경우에도 시간 복잡도가 O(logN)임
  
  노드에는 2개 이상의 데이터(key)가 들어갈 수 있으며, 항상 정렬된 상태로 저장됨
  
  Binary Tree를 확장한 형태로 더 많은 자식을 가질 수 있음
  
  
* 사용하는 경우

  데이터베이스(인덱스), 파일 시스템
  
      대용량 데이터 처리 시, 하나의 노드에 많은 데이터를 가지면 큰 장점이 됨
      
      대용량 데이터는 메모리보다 블럭 단위로 입출력되는 하드디스크나 SSD에 저장되기 때문
      
      -> 한 블럭이 1024 바이트일 때, 2바이트를 읽으나 1024 바이트를 읽으나 동일한 입출력 비용(한 블럭)이 발생함
      
* 규칙

  * 하나의 노드에 여러개의 자료가 배치되는 트리구조임
  
  * 한 노드에 M개의 자료가 배치되면 M차 B Tree라고 함

  * 특정 노드의 자료수가 N이라면 자식 수는 N + 1이어야 함
  
  * 루트 노드는 적어도 2개 이상의 자식을 가짐
  
  * 루트 노드를 제외한 모든 노드는 M / 2개 이상의 자료를 가짐 \
    ex) 7차 B Tree인 경우 루트 노드를 제외한 모든 노드는 3개 이상의 자료를 가짐
  
  * 모든 리프 노드들은 같은 레벨에 존재함
  
  * 외부 노드로 가는 경로의 길이는 모두 같음
  
  * 입력 자료는 중복될 수 없음
  
* 장점

  삽입/삭제 후에도 균형 트리를 유지함
  
  균등한 탐색 속도를 보장함
  
  저장 장치의 효율성을 높임
  
* 단점

  노드 삽입/삭제 시 트리의 균형을 유지하기 위한 츄가 연산(재분배, 병합) 필요
  
  순차탐색 시 중위순회로 비효율적임

### B+ Tree

* B+ Tree란?

  B+ Tree는 B- Tree의 확장 개념으로 데이터의 빠른 접근을 위해 index 역할을 하는 비단말노드가 추가됨
  
  모든 데이터는 리프 노드에만 존재하며 모든 리프 노드는 연결리스트로 구성되어있음 \
  -> 리프 노드를 B- Tree구조 + 연결리스트로 구현된 색인 구조로 구성하여 순차탐색 시 B- Tree보다 효율적임
  
  데이터의 삽입/삭제는 리프 노드에서만 발생함
  
* 장점

  블럭을 더 효율적으로 사용할 수 있음
  
  leaf 노드끼리 연결리스트로 연결되어 있어 순차탐색, 범위탐색에 매우 유리함
  
* 단점

  B Tree의 경우 최상 케이스는 루트에서 탐색을 끝낼 수 있지만, B+ Tree는 무조건 leaf 노드까지 내려가야함
  
### B Tree vs B+ Tree

  B Tree는 노드에 데이터가 저장됨
  
  B+ Tree는 index노드와 leaf노드로 분리되어 저장됨
  
  B Tree는 각 노드에 key와 data가 모두 들어갈 수 있으며 data는 disk block으로 포인터가 될 수 있음
  
  B+ Tree는 각 노드에 key만 들어가며 data는 모두 leaf 노드에만 존재함