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

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/71b74e6d-5762-4022-8c5e-9b0cbb26d6e8)

- P : 물건이 있다면, 물건을 가지고 가라. 물건이 없다면 Q(대기실)에서 기다려라.
  - Spin과 차이점 : 물건이 없다면, while문에서 돈다.
- V : Q에서 기다리는 애가 있다면, 기다리는 애를 깨워서 준다.

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/05a80ec9-917a-480f-92d2-1fda8000fa0e)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/223143d9-e660-4088-8012-aacd970a45fe)
- CS에서 나오면 큐에서 기다리던 프로세스를 깨워준다.

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/e2a4569c-78fd-43a2-b340-9dda82fa39f5)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/88cbca93-bc3b-423a-b06c-356323b8fd3e)
- CS가 끝나면 대기 중인 프로세스를 깨운다.

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/46f4dd43-56b8-4f40-9e4c-0330725f0e92)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/3fadc460-526e-4932-a5f5-39b1e1c30dbf)

- buffer는 한 번에 한 프로세스만 접근할 수 있다.
- ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/99a82a34-cfa2-423e-843d-ca4ba9591817)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/d48a06f1-52cb-4a2a-a691-cceb4899b337)
- 생산자는 공간이 있는지 확인하고, Consumer은 물건이 있는지 확인한다.
- 생산자가 물건을 생산했으면 대기하고 있는 Consumer가 있는지 확인 후 wake up 시킨다.
![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/397534dc-370c-41e5-a2c1-e20bcd701099)
- Reader와 Writer은 서로 각자 움직인다.
- Reader가 읽는 동안 Writer가 갱신하지 못한다.
![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/d3d59e05-6b79-4d58-a8c3-9e8ec10ecb04)
- enter할 때, reader가 0이라면, writer 잠시 기다려!
- exit할 때, reader가 0이라면 writer 너 작동해도 되! reader가 0이 아니라면, 그대로 기다리고 있어!

<h1> Semaphore </h1>

- <b> No busy waiting </b>
  - 기다려야 하는 프로세스는 block(asleep) 상태가 됨
  - 어떤 일이 있어도, while문을 돌지 않음
- <b> Semaphore queue에 대한 wake-up 순서는 비결정적
  - Starvation problem(기아상태)
