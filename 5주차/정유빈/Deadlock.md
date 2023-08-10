![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/22cc7de6-e69b-4990-aed5-ba10224b129f)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/e249061c-4005-46f4-ae63-65000f7e065a)
- deadlock 상태는 자원 가능성 zero
- starvation  상태는 cpu 자원 할당을 기다리는 것

<h1> 자원의 분류 </h1>

- 일반적 분류
  - 하드웨어 자원 vs 소프트웨어 자원
 
  ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/e59714c7-4182-4b1e-9791-928254e03aab)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/a044541b-256c-430d-b0a5-630da169d448)
- Preemptible resources : 빼앗긴 후, 다시 돌아와도 문제가 발생하지 않는 자원
- Non-preemptible resources : 선점 당하면, 이후 진행에 문제가 발생하는 자원

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/ad4ac8b8-2f75-4b2a-b32b-8d4aa4ced7f3)
- 한 번에 모두를 다 주는 것 vs 나누어 주는 것

 ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/1f9a9a6c-d1fc-4e54-b36a-725a1a18292b)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/e6a9a33d-94a2-456e-93f1-04fa518f1766)

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/12c16501-48e4-49c8-ad16-e59ef7f667ca)
- 비선점 : 한번 할당받으면, 남을 못 주는 것
- Exclusive allocation resources : 혼자 쓰는 것
- 할당 단위는 영향을 미치지 않음

![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/8df7ac4f-aae8-4413-82f3-9b055b096ca3)


<h1> Deadlock Model(표현법) </h1>

- Graph Model
- State Transition Model

- ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/2fc6885c-5a9e-4172-89be-c19a14d72770)

