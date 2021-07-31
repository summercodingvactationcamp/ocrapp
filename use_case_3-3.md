## Use Case UC-03-3: 결과 출력
**1) Related Requirements** : REQ-14, REQ-15

**2) Initiating Actors** : Back-end Controller

**3) Actor's Goal** : UC-03-01에서 쿼리한 뒤 넘겨받은 클래스 인스턴스를 통해 html 테이블로 출력한다.

**4) Participating Actors** : Web-service

**5) Preconditions** : 연령대별 복지 정책 데이터베이스 스키마가 존재하고 OCR로부터 올바른 결과를 얻을 수 있어야 한다.

**6) Postconditions** :  None

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                                                 |
| --------- | ---- | ------------------------------------------------------------ |
|    →       | 1    | Back-end controller가 이전 UC-03-02에서 객체 인스턴스를 넘겨 준다. |
| ←         | 2    | 넘겨 받은 객체를 잘 파싱하여 html 테이블을 생성한 뒤 웹에 출력한다. |



**8) Flow of Events for Extensions (Alternate Scenarios)**

5a. 넘겨 받은 객체의 데이터가 None인 경우

| Direction | n    | Actor Action                                   |
| --------- | ---- | ---------------------------------------------- |
| ←         | 1    | 해당하는 복지 정책이 없음을 알림한다.       |
