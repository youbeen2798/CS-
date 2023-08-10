![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/528b1de6-48eb-4267-858e-c6cafa7d06e0)### Blocked/Asleep state
프로세스가 필요한 자원, 특정 이벤트를 기다리는 상태 </br>

</br>

### Deadlock state
프로세스가 발생 가능성이 없는 이벤트를 기다리는 경우 </br>
  - 프로세스가 Deadlock 상태에 있음

시스템 내에 Deadlock에 빠진 프로세스가 있는 경우 </br>
  - 시스템이 Deadlock 상태에 있음

</br>
</br>

## Deadlock vs Starvation 

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/236071b8-c196-4e20-93f4-fdfe9950bf37)

### Starvation (기아상태)
우선순위가 높은 프로세스들에게 우선순위를 빼앗겨 CPU를 무한정 기다리게 되는 상태이다. </br>

### Deadlock (교착상태)
자원이나 이벤트를 기다리는데 발생 가능성이 없는 것을 기다리는 상태이다. </br>

</br></br></br>

## 자원
### 일반적 분류
- Hardware resource VS Software resource

### 다른 분류법
- 선점 가능 여부에 따른 분류
- 할당 단위에 따른 분류
- 동시 사용 가능 여부에 따른 분류
- 재사용 가능 여부에 따른 분류

</br>
</br>

## 선점 가능 여부에 따른 분류
### Preemptible resources
선점 당한 후, 돌아와도 문제가 발생하지 않는 자원 (빼앗겼다가 다시 돌아와서 일했을 때 문제가 발생하지 않는 자원) </br>
Processor, memory 등 -> CPU는 Context Swiching / memory는 Swap-device </br>

</br>

### Non-preemptible resources
선점 당하면, 이후 진행에 문제가 발생하는 자원
- Rollback, restart 등 특별한 동작이 필요

E.g., dist drive 등 </br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/a1eadccc-6903-426b-815d-9176d3b0180c) </br>

- 데이터를 기록하고 있는 도중 누군가 빼앗어가면 데이터가 날라간다. (즉, 선점 당하면 데이터가 날라가는 문제가 생김)

</br>
</br>


## 할당 단위에 따른 분류
### Total allocation resource (전체를 다줌)
자원 전체를 프로세스에게 할당 </br>

E.g., Processor, disk drive 등  </br>
(CPU 나 Disk는 1:1 임) </br>

</br>

### Partitionaled allocation resources
하나의 자원을 여러 조각으로 나눠, 여러 프로세스들에게 할당 </br>

E.g., Memory 등 (메모리는 프로세스별로 나누어 사용하게 해줌) </br>


</br>
</br>

## 동시 사용 가능 여부에 따른 분류
### Exclusive allocation resources
한 순간에 한 프로세스만 사용 가능한 지원  </br>

E.g., Processor, memory, disk drive 등  </br>
(memory는 본인에게 할당된 영역만 사용함) </br>

</br>

### Shared allocation resource
여러 프로세스가 동시에 사용 가능한 자원 </br>

E.g., Program(sw), shared data 등  </br>
(source code, .exe) </br>

</br>
</br>

## 재사용 가능 여부에 따른 분류
### SR (Serially-reusable Resources)
시스템 내에 항상 존재 하는 자원 </br>

사용이 끝나면, 다른 프로세스가 사용 가능 </br>

E.g., Processor, memory, dist drive, program  등 </br>

</br>

### CR (Consumable Resources)
한 프로세스가 사용한 후에 사라지는 자원 </br>

E.g., signal, message 등 </br> 

</br>
</br>

### 데드락과 자원은 밀접한 관계가 있다. 

### Deadlock을 발생시킬 수 있는 자원의 형태
Non-preemptible resources </br>
- 한번 할당 받으면 뺏을 수 없기 때문에
  
Exclusive allocation resources </br>
- 혼자 쓰기 때문에

Serially reusable resources </br>
- SR, CR 둘다 영향이 있으나 CR은 고려하기 힘듬

* 할당 단위는 영향을 미치지 않음

</br>

### CR을 대상으로 하는 Deadlock model
너무 복잡


</br>
</br>
</br>

## Deadlock 발생의 예
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/4950485e-45ff-44c6-a7e6-7ac34eb9d0d6)

</br>
</br>

## Deadlock Model(표현법)
### Graph Model
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/97abfdad-0172-4d15-b260-60011fc8f9a6) </br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/dc1f7ca3-a822-4032-ad02-3bbcc7232001) </br>


</br>

### State Transition Model
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/95c91c29-962e-4b5c-b1c7-8d31b676c99f) </br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/aa73e8f6-a92e-465d-8908-bbad10ea6b77) </br>
- S00, S01 .... 이렇게 되어있는 애들이 S프로세스1번프로세스2번
- S33에서 데드락이 발생함


</br>
</br>

## Deadlock 발생 필요 조건
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/7c7a882b-ef00-4349-aa3c-bc96b3483770)
- 내가 필요한 자원을 다 가지고 있거나, 자원이 하나도 없다면 deadlock 발생 X
