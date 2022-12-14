# DeadLock(교착상태, 데드락)

### DeadLock이란?

  두 개 이상의 프로세스나 스레드가 서로 자원을 얻지 못해 다음 처리를 하지 못하는 상태
  
  무한히 자원을 기다리는 기아상태가 발생함
  
### DeadLock이 발생하는 경우

  시스템적으로 한정된 자원을 여러 곳에서 사용하려고 할 때 발생하게 됨
  
  ex) 프로세스 1, 2가 자원 a, b를 모두 필요로 할 때, 프로세스 1이 자원 a를 얻고, 프로세스 2가 자원 b를 얻게 됨
  
  -> 이후 프로세스 1이 자원 b를, 프로세스 2가 자원 a를 무한정 기다리게 됨 : DeadLock 발생
  
### DeadLock 발생 조건

4가지 조건이 모두 성립해야만 DeadLock 발생

  * 상호 배제(Mutual exclusion)
  
    자원은 한 번에 한 프로세스만 사용할 수 있음
    
  * 점유와 대기(Hold and wait)
  
    최소 하나의 자원을 점유하고 있으며, 다른 프로세스에 할당되어 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 존재
    
  * 비선점(Non preemtion)
  
    다른 프로세스에 할당된 자원을 사용이 끝날 때까지 강제로 빼앗을 수 없음
    
  * 순환 대기(Circular wait)
  
    프로세스 집합에서 자원을 순환 형태로 대기하고 있음
    
  ###  DeadLock 해결 방법
  
  * 예방과 회피

  1. 예방(Prevention)

      교착 상태 발생 조건 중 하나 이상을 제거하여 교착 상태를 해결하는 방법

      자원 낭비가 가장 심한 방법

  2. 회피(Avoidance)

      교착 상태가 발생하기 전 교착 상태를 예측하고 회피하는 방법

      대표적인 예는 은행원 알고리즘(Banker's Algorithm)이 있음

  * 탐지 & 회복

  1. 탐지(Detection)

      교착 상태를 허용하되 자원 할당 그래프와 탐지 알고리즘을 사용해 교착 상태를 탐지하며 복구하는 방법

      탐지 알고리즘을 너무 자주 호출할 경우 오버헤드가 커지기 때문에 적절한 시점과 주기에 호출할 필요가 있음

  2. 회복(Recovery)

      교착 상태를 일으킨 프로세스를 종료하거나 할당된 자원을 해제시켜 상태를 회복시키는 방법

      교착 상태의 프로세스 전체를 종료하거나 상태가 개선될 때까지 프로세스를 하나씩 종료

      교착 상태의 프로세스가 점유하고 있는 자원을 선점해 다른 프로세스에게 할당

      우선 순위가 낮은 프로세스나 수행 횟수가 적은 프로세스 위주로 프로세스 자원 선점
        