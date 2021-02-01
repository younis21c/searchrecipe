# Search Recipe

## 서비스 시나리오
### 기능적 요구사항
- 회원이 레시피를 검색한다.
- 회원이 검색된 내용을 보고 부족한 재료를 주문한다.
- 주문이 되면 주문 내역에 대한 배송이 시작된다.
- 배송 정보는 주문 정보에 업데이트 된다.
- 고객이 주문을 취소할 수 있다.
- 주문이 취소되면 배송도 취소된다.
- 고객이 주문상태를 중간중간 조회한다.

### 비기능적 요구사항
- 트랜잭션
    - 고객이 주문을 취소하면 주문도 즉시 주문이 취소된다.
    - Sync 호출
- 장애격리
    - 배송 서비스가 정상 기능이 되지 않더라도 주문을 받을 수 있다. Async (event-driven), Eventual Consistency 
    - 주문시스템이 과중되면 사용자를 잠시동안 받지 않고 주문을 잠시후에 하도록 유도한다 Circuit breaker, fallback
- 성능
    - 고객이 배달상태를 주문시스템에서 확인할 수 있어야 한다. CQRS 

## 분석/설계
### EventStorming 결과
<img src="./images/2021-01-31 155439.png" />