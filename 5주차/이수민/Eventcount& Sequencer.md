# Eventcount& Sequencer

### 은행의 번호표와 비슷한 개념

</br>

### Sequencer
- 정수형 변수
- 번호 뽑는 기계
- 생성시 0으로 초기화, 감소하지 않음
- 순서 유지
- ticket() 연산으로만 접근 가능 (번호표 뽑는 행위)

</br>

### ticket(S)
- 현재까지 ticket() 연산이 호출 된 횟수를 반환
- Indivisible operation


![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/69f67502-ad42-4c35-9c63-27576e0a4bc5)



</br>
</br>



### Eventcount
- 정수형 변수
- 생성시 0으로 초기화, 감소하지 않음
- 특정 사건의 발생 횟수로 기록
- read(E), advance(E), await(E,v) 연산으로 접근 가능


### read(E)
- 현재 Eventcount 값 반환

### advance(E)
- E <- E + 1 (번호가 1증가 됨)
- E를 기다리고 있는 프로세스를 깨움 (wake-up) - 증가된 번호를 기다리고 있는 프로세스를 깨운다.

### await(E,v)
- v는 정수형 변수
- if(E<v) 이면 E에 연결된 Qe에 프로세스 전달(Push) 및 CPU scheduler 호출 (대기실에서 내 번호를 기다린다.)

![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/40b39ed5-d1a1-4a12-bc47-9496fa534d16)

</br>
</br>


### Mutual exclusion
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/4465601c-667c-44f9-9dd0-a67adca8b1c8)

- 세마포어의 문제점인 `Starvation (기아상태)`를 해결해준다.

</br>
</br>

### Producer-Consumer Problem
![image](https://github.com/leesuuuuumm/Deep-CS-study_for_interview/assets/58407737/9bd50dc2-0720-4da5-84f7-643c2e8ccf31)

</br>

### 특징
- No busy waiting
- No starvation (: FIFO Scheduling for Qe)
- Semaphore 보다 더 low-level control이 가능 (순서 컨트롤이 가능)
