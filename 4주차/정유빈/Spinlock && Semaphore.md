<h1> OS supported SW solution </h1>

- HW solution은 Busy waiting 문제를 해결하지 못함

<h1> Spinlock </h1>

- 정수변수
- 초기화, P(), V() 연산으로만 접근 가능
  - 위 연산들은 indivisibile(or atomic) 연산
  - OS support
  - 전체가 한 instruction cycle 수행 됨
 
    ![image](https://github.com/youbeen2798/Deep-CS-study_for_interview/assets/62228401/1c566bad-9917-4670-bccc-d540ccb4ea7d)
