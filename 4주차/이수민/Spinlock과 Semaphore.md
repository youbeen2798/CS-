# Spinlock

### 정수형 변수
### 초기화, P(), V() 연산으로만 접근 가능
- 위 연산들은 indivisible (or atomic) 연산
  - P와 V를 OS가 보장함 
  - 전체가 한 instruction cycle에 수행 된다.
  ![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/754ba6ef-e731-4814-b645-4e156d42e545)

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/9fef4555-7930-4f59-9c43-3e54712b36d8)

</br>

### Spinlock은 멀티 프로세서에서만 가능하다.
### Busy waiting 문제 해결되지 않음 

</br>


# Semaphore
### Dijkstra가 제안함
### Busy waiting 문제를 해결함
### 음이 아닌 정수형 변수 (S)
- 초기화 연산, P(), V() 연산으로만 접근 가능
  - P: Probern (검사)
  - V: Verhogen (증가)
 
### 임의의 S 변수 하나에 Ready queue 하나가 할당 됨 (SpinLock과의 차이점) 

</br>

## 종류
### Binary semaphore
- S가 0과 1 두 종류의 값만 갖는 경우
- 상호배제나 프로세스 동기화의 목적으로 사용

</br>

### Counting semaphore
- S가 0이상의 정수값을 가질 수 있는 경우
- Producer-Consumer 문제 등을 해결하기 위해 사용
  - 생산자 - 소비자 문제

</br>
</br>


![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/45d98949-f085-47dd-a929-d7896a99d616)

</br>

## 세마포어로 해결 가능한 동기화 문제들
1. 상호배제 문제
- Mutual exclusion

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/29690b21-1756-4503-86d0-dc226154d4de)








</br>
</br>




2. 프로세스 동기화 문제
- process synchronization problem

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/d728e822-abe5-44d5-8aef-5dcc834105e7)


</br>
</br>


3. 생산자-소비자 문제
- producer-consumer problem

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/a8a04299-f565-4834-8f0f-4b1c597f3118)

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/ed295f47-21ab-45d1-8b4f-264df7f4b611)


</br>
</br>
 
4. Reader-writer 문제
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/4b0f5959-a0e0-408c-ad36-1ea84e141062) </br>

- Reader들은 동시에 접근 가능
- Writer들은 동시에 접근 하려면 상호배제가 필요하다.

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/fd2ae94d-07e2-449f-839e-f5eaf4205f47)

5. Dining philocopher problem (철학자들의 저녁식사 문제)

</br>
</br>
   
## 장점
### No busy waiting
- 기다려야 하는 프로세스는 block(asleep) 상태가 된다.

## 단점
### Semaphore queue에 대한 wake-up 순서는 비결정적이다.
- wake up 할 때 그들중 한명 깨우기 때문에 어떠한 애는 계속 밀릴 수 있어서 "Starvation problem" 발생 

