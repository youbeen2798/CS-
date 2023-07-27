<h1> Mutual Exclusion Solutions </h1>

<h3> Synchronization Hardware </h3>

- TestAndSet(TAS) instruction
  - Test와 Set을 한 번에 수행하는 기계어
  - Machine instruction
    - Atomicity, Indivisible
    - <b> 실행 중 interrupt를 받지 않음(preemption 되지않음)
  - Busy waiting
    - Inefficient
