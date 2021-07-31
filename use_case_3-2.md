## Use Case UC-03: DB 쿼리

**1) Related Requirements** : DB 스키마 업데이트 필요

**2) Initiating Actors** : Back-end Controller

**3) Actor's Goal** : OCR 결과로부터 알맞은 정보를 조회한 뒤 웹에 출력한다.

**4) Participating Actors** : DB

**5) Preconditions** : 연령대별 복지 정책 스키마가 존재하고 OCR로부터 올바른 결과를 얻을 수 있어야 한다.

**6) Postconditions** :  None

**7) Flow of Events for Main Success Scenario**

| Direction | n    | Actor Action                                                 |
| --------- | ---- | ------------------------------------------------------------ |
| →         | 1    | Back-end Controller는 OCR 결과를 넘겨 받는다 |
|           | 2    | 넘겨 받은 결과 중 연령대를 확인하여 DB에 입력받은 나이 값으로 쿼리를 한다                  |
|           | 3    | DB에 쿼리한 결과를 새로운 객체 인스턴스로 저장한다.                           |
| ←         | 4    | 시스템(Back-end controller)에 객체 인스턴스를 넘겨준다. |

**8) Flow of Events for Extensions (Alternate Scenarios)**

a) 조회할 DB 스키마가 존재하지 않는 경우

| Direction | n    | Actor Action                                        |
| --------- | ---- | --------------------------------------------------- |
| ←         | 1    | 해당 쿼리에 대응하는 적절한 스키마가 존재하지 않음을 출력한다. |

b) 테이블이 비어있는 경우

| Direction | n    | Actor Action                                        |
| --------- | ---- | --------------------------------------------------- |
| ←         | 1    | 해당 쿼리에 대응하는 테이블이 비어있음을 알린다. |
