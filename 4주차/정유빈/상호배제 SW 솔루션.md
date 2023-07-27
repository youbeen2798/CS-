<h1> SW solutions </h1>


<h3>  Dekkers's algorithm </h3>

- Two process ME를 보장하는 최초의 알고리즘

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/a0f17a69-bc5e-40ff-b4f1-9abb2fcf1b4b)

- <b> Dekkers's algorithm보다 간단하게 구현 </b>

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/33462e59-905f-43fc-946f-984595158ab5)

<h3> N - Process Mutual Exclusion </h3>

- 다익스트라
  - 최초로 프로세스 n개의 상호배제 문제를 소프트웨어적으로 해결
  - 실행 시간이 가장 짧은 프로세스에 프로세서 할당하는 세마포어 방법, 가장 짧은 평균 대기시간 제공
![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/396b762f-3f72-401e-8bcb-9b71881fdca7)
  - ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/79ee81e7-7bf7-4162-b376-c91c46b90ef9)

<H3> SW solution들의 문제점 </H3>

1. 속도가 느림
2. 구현이 복잡함
3. ME primitive 실행 중 preemption 될 수 있음
  - 공유 데이터 수정 중은 interrupt를 억제함으로써 해결 가능
    - overhead 발생
4. Busy waiting
  - Inefficient
