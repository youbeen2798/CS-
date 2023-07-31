<h1> OS supported SW solution </h1>

- HW solution은 Busy waiting 문제를 해결하지 못함

<h1> Spinlock </h1>

- 정수변수
- 초기화, P(), V() 연산으로만 접근 가능
  - 위 연산들은 indivisibile(or atomic) 연산
  - OS support
  - 전체가 한 instruction cycle 수행 됨
 
    ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/1c566bad-9917-4670-bccc-d540ccb4ea7d)

- P : 물건을 꺼내가는 과정
- V : 물건을 반납하는 과정

- ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/7eb40d16-9872-494d-851e-2afc8b440963)
- 단점 
  - 멀티 프로세스만 사용 가능
  - CS에서 멈추게 되면, 다른 프로세스 사용 불가능 -> <b> Busy Waiting </b>

<h1> Semaphore </h1>

- BusyWaiting 문제 해결 가능
- 음이 아닌 정수형 변수(S)
  - 초기화 연산, P(), V()로만 접근 가능
  - P: Problem(검사) - 들어가기 전에 검사
  - V: Verhogen(증가) - 나가고 검사
  - 임의의 S 변수 하나에 ready queue 하나가 할당 됨

- <b> Binary semaphore </b>
  - S가 0과 1 두 종류의 값만 갖는 경우
  - 상호 배제나 프로세스 동기화의 목적으로 사용
 
- <b> Counting semaphore </b>
  - S가 0이상의 정수 값을 가질 수 있는 경우
  - Producer-Customer 문제 등을 해결하기 위해 사용
    - 생산자-소비자 문제
