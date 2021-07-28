## Use Case UC-03: 결과 출력
**1) Related Requirements** : REQ-1, REQ-2, REQ-3, REQ-4, REQ-5

**2) Initiating Actors** : OCR Module

**3) Actor's Goal** : OCR 결과로부터 알맞은 정보를 조회한 뒤 웹에 출력한다.

**4) Participating Actors** : Web-service module, 유저

**5) Preconditions** : 연령대별 복지 정책 스키마가 존재하고 OCR로부터 올바른 결과를 얻을 수 있어야 한다.

**6) Postconditions** :  None

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                                                 |
| --------- | ---- | ------------------------------------------------------------ |
| →         | 1    | OCR 모듈은 OCR 결과를 해당 모듈에 전달해준다 |
|           | 2    | 넘겨 받은 결과 중 연령대를 확인하여 DB에 입력받은 나이 값으로 쿼리를 한다                  |
|           | 3    | DB에 쿼리한 결과를 모두 메모리에 저장한다                                |
| ←         | 4    | 모듈은 최종적으로 쿼리한 결과를 동적으로 테이블로 생성하여 사용자에게 출력해준다 |



**8) Flow of Events for Extensions (Alternate Scenarios)**

5a. OCR에서 잘못된 데이터 값을 받아왔을 경우 (나이의 범위가 잘못된 경우)

| Direction | n    | Actor Action                                   |
| --------- | ---- | ---------------------------------------------- |
| ←         | 1    | 유저에게 사진을 다시 찍어달라고 요청한다          |
