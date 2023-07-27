<h1> Mutual Exclusion Solutions </h1>

<h3> Synchronization Hardware </h3>

- TestAndSet(TAS) instruction
  - Test와 Set을 한 번에 수행하는 기계어
  - Machine instruction
    - Atomicity, Indivisible
    - <b> 실행 중 interrupt를 받지 않음(preemption 되지않음) </b>
  - Busy waiting
    - Inefficient
![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/1ea5a282-ae0e-4e75-9714-1d7f6af9e68b)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/95b85fea-3f64-444f-b296-716cfc8fc617)

- 3개 이상의 프로세스 경우, Bounded waiting 조건 위배
- 1번 프로세스가 CS를 빠져나가고, lock을 false로 만들었을 때, while문에서 프로세스 2와 프로세스 3이 기다린다면 같이 Critical Section 접근
![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/50dc8905-3357-4259-9f4b-655d35cfc6b4)
- 기다린 순서대로 Critical Section에 접근 가능

- <b> 장점 </b>
  - 구현 간단
-  <b> 단점 </b>
  - Busy waiting
    - Inefficient
   
- <b> Busy waiting 문제를 해소한 상호배제 기법 </b>
   - Semaphore
       - 대부분의 OS들이 사용하는 기법
