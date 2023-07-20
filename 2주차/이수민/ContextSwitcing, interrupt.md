## 예상 질문
1. ContextSwitching 과정에 대해 설명해주세요.
- 인터럽트나 시스템 콜이 걸렸을 때 OS는 현재 running중인 프로세스를 저장한다. 실행중이었던 프로세스 상태 및 정보를 PCB에 저장하고, 다음 실행할 프로세스의 상태 및 정보를 PCB에 읽어 레지스터에 옮기는 과정이다>

</br>

2. 코드, 데이터, 스택, PCB 정보와 CPU에서의 작업 내용에 관한 정보는 각각 어디에 저장이 되냐?
- 코드, 데이터, 스택, pcb정보는 메모리 내에 존재함으로 별도로 저장할 필요가 없지만, CPU에서의 작업 내용에 관한 정보 CPU register context는 CPU에 존재하는데 이를 PCB블록에 저장한다.

</br>

3. Context Restoring이란?
- Ready Queue에 있는 프로세스를 꺼내 다시 프로세서에 올릴 수 있는데, 이때 프로세스를 다시 올리기 위해 저장했던 Context를 불러와 복구하는 작업이다.

</br>


4. interrupt 처리 과정
- 프로세스를 중단하고 context saving(현재 상태 저장)한다. 그리고 인터럽트 핸들러가 인터럽드가 발생한 장소, 원인 파악하여 인터럽트 서비스 할건지 결정한 후 처리한다.

</br>

5. interrupt 서비스와 interrupt 서비스 루틴(= 인터럽트 핸들러) 차이
- 인터럽트가 발생하면 어떻게 할지 결정하는 것은 ISR
- 이렇게 인터럽트가 걸리고 처리하는 과정을 통틀어 Interrupt service라 한다.

</br>

6. ContextSwitching 발생하는 비용
- cache 초기화
- Memory Mapping 초기화
- Kernel은 메모리 접근을 위해서 항상 실행되어야 함
- context switching 때, 해당 CPU는 아무 작업을 하지 못하기 때문에  context switching 이 자주 일어나면 오버헤드가 많이 발생해서 오히려 효율과 성능이 떨어질 수 있다.

- thread가 더 나은 이유-> stack영역만 변경해주면 돼서

