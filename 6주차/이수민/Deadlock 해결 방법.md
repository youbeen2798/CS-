# Deadlock 발생 필요 조건
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/e200e69b-8f54-4469-b3b2-b41a067b218a)

</br>

발생하지 않게 하려면 위 4개중 하나 없애버리기!! 

</br>

# Deadlock 해결 방법
## Deadlock prevention methods (교착상태 예방)
Deadlock을 절대 발생 시키지 않겠다. </br>

4개의 deadlock 발생 필요 조건 중 하나를 제거한다. </br>

### 1. 모든 자원을 공유 허용
- Exclusive use of resources 조건 제거
- 현실적으로 불가능

</br>

### 2. 모든 자원에 대해 선점 허용
- Non-preemptible resources 조건 제거
- 현실적으로 불가능
- 유사한 방법
  - 프로세스가 할당 받을 수 없는 자원을 요청한 경우, 기존에 가지고 있던 자원을 모두 반납하고 작업 취소
    - 이후 처음(또는 check-point)부터 다시 시작
  - 심각한 자원 낭비 발생 -> 비현실적

</br>

### 3. 필요 자원 한번에 모두 할당 (Total allocation)
- Hold and wait 조건 제거
- 자원 낭비 발생
  -  필요하지 않은 순간에도 가지고 있음
- 무한 대기 현상 발생 가능
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/ed32b954-dbfc-4376-9508-cea98d381ec2)


</br>

### 4. Circular wait 조건 제거
- Totally allocation을 일반화 한 방법
- 자원들에게 순서 부여
- 프로세스는 순서의 증가하는 방향으로만 자원 요청 가능
- 자원 낭비 발생

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/ce12600b-92ee-4a2b-99e9-2ecd36453de6)

</br>
</br>


## Deadlock avoidance method (교착상태 회피)
시스템의 상태를 계속 감시한다. </br>
시스템이 deadlock 상태가 될 가능성이 있는 자원 할당 요청을 보류한다. </br>
시스템을 항상 safe state로 유지한다. </br>

</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/0fa2e296-d9e1-4d6f-b28e-3efc75868b96)


</br>

### 가정
- 프로세스의 수가 고정됨
- 자원의 종류와 수가 고정됨
- 프로세스가 요구하는 자원 및 최대 수량을 알고 있음
- 프로세스는 자원을 사용 후 반드시 반납한다.

### -> Not practical

</br>

### Dijkstra's algorithm
Banker's algorithm </br>
- Deadlock avoidance를 위한 간단한 이론적 기법
- 가정
  - 한 종류(resource type)의 자원이 여러 개(unit)
- 시스템을 항상 safe state로 유지

 
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/fc01dc0b-5c6d-4f81-8042-0900aca40c33) </br>
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/7538ea56-fcbd-45e4-9afd-0cb3a290b580)  </br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/fe69c403-29fa-47e2-84ff-4cdf9218a0bc)  </br>

- 자원을 주었다고 가정해보고 시뮬레이션 해 본 결과, safe squence가 있으면 OK , 없으면 거절


</br>
</br>

### Habermann's algorithm (자원이 여러개)
- Dijkstra's algorithm의 확장
- 여러 종류의 자원 고려
  - Multiple resource types
  - Multiple resource units for each resource type
- 시스템을 항상 safe state로 유지

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/eb26ff62-7576-49f7-a1c3-3cd86bea2154) </br>
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/b6e08f98-f493-4f7d-a755-f9a0101f8094) </br>
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/b8d6647b-70be-4574-aa1a-f056a6e377a3) </br>


</br>

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/5beaad5d-4a10-459d-8b2b-0ad2721ae94d)

