 ![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/0ff5ef66-6077-40bd-a89c-3888f21df14e)

## High-level Mechanism

### Monitor
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/a0588e13-af62-4b8c-a58b-d6fc0782eb6b) 

### Language-level constructs

### Object-Oriented concept과 유사

### 사용이 쉬움


# Monitor
### 공유 데이터와 Critical section의 집합
### Conditional variable
- wait(), signal(), operations
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/dbbed11c-dcd7-4528-adb2-269bac1c5f01)


## Monitor 구조
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/7d0a8104-e2d1-4da6-bf7f-ba6280f6ed4a)


## 특징
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/7adfe6cf-74ff-4dac-beab-1cddbf1c12d8)
- Language가 support 해준다.

## How to support?
### 1. 자원 할당 문제
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/93ad0b9b-597f-43aa-869f-66242147198e)
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/876c3199-361d-4918-aeb2-f943b5086047)
- 코드는 이렇게 구현!!! 생각하는대로 짤 수 있음

### 2. 자원 할당 시나리오 (내부 동작)
- 자원 R 사용 가능
- Monitor 안에 프로세스 없음

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/f3bdf987-468f-4b63-8656-931f849faeb9)
- 프로세스 Pj가 모니터 안에서 자원 R을 요청함

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/beedd170-4d55-4d4a-9560-64b5aec76b17)
- 자원 R이 Pj에게 할당 됨
- 프로세스 Pk가 R 요청, Pm 또한 R요청

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/ec69868a-f040-44d1-8bf3-accac023fb2e)
- Pj가 R 반환
- R_Free.signal() 호출에 의해 Pk가 wake up

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/b46ac09e-218a-4a73-959a-215e8c99b1a7)
- 자원 R이 Pk에게 할당 됨
- Pj가 모니터 안으로 돌아와서, 남은 작업 수행

</br>

## Producer-Consumer Problem
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/4f8d0cd5-9260-4cb0-aaf9-9896fd811922)
- 물건을 넣는 애 / 물건을 빼는 애

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/c2857754-30e7-4240-9e4c-2d7d4538e096)
- 코드로 구현

## Reader-Writer Problem
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/9b2519f9-31c1-4fca-b195-fdcca3c9cd22)
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/9f872c6c-36b2-4c6d-8f0c-b24d9c9c2f88)


## Dingig philosopher problem
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/4481888a-7485-4d37-81c2-a19bcd075787)
- P: 프로세스 / fork: 공유 데이터

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/bc1f3fd6-d445-4f6f-9bfc-f33f7412897d)
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/b21419ba-80e2-40ff-84f2-8ae87cb9c6e4)

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/bfe63d90-e1da-4dc9-bca9-7f04184ad3f1)


## Monitor 장/단점
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/3122e58a-0a7b-414c-95ba-aa63984945f3)
- 지원하는 언어: 기계어로 번역(컴파일러)
- Open MP 
