<h1> Deadlock </h1> 

- <b> blocked / asleep state </b>
  - 프로세스가 특정 이벤트를 기다리는 상태
  - 프로세스가 필요한 자원을 기다리는 상태

- <b> deadlock state </b>
  - 프로세스가 발생 가능성이 없는 이벤트를 기다리는 경우
    - 프로세스가 deadlock 상태에 있음
  - 시스템 내에 deadlock에 빠진 프로세스가 있는 경우
    - 시스템이 deadlock 상태에 있음

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/4b29dcab-7220-43e5-af7a-25c5315f7b65)
- DeadLock vs Starvation
  - DeadLock : blocked 상태에서 <b> 가능성이 zero </b> 인 자원 혹은 event를 기다리는 상태
  - Starvation : ready 상태(cpu로부터 자원을 할당받기를 기다리는 상태)에서 운이 없어서, 우선순위가 계속 밀리는 상태
