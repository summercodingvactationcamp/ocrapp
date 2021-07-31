# Domain Model for UC-xx : 결과 출력 

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name    |
| ------------------------------------------------------------ | ---- | --------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller      |
| OCR module에서 받아온 나이, 지역구의 데이터를 array 형태로 저장한다                         | K    | Array Data           |
| 데이터베이스에 받아온 array 데이터를 사용하여 DB에 쿼리한다                  | D    | QuestionDB     |
| 쿼리한 Value를 클래스 인스턴스로 저장하는 모듈                       | D    | SaveResult     |
| 데이터베이스로부터 쿼리해 온 결과를 html 테이블 형태로 표시한다                            | D    | Viewer          |

**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| OCR Module <-> Controller     | OCR 모듈이 Controller에 요청을 하여 array를 전달한다.                      | provides data     |
| Controller <-> SearchDb      | Controller가 array 데이터를 searchDB에 넘겨주어 query를 실행한다              | conveys data     |
| SearchDb <-> SaveResult | SearchDB에서 받은 결과를 SaveResult에서 객체 인스턴스로 저장한다                |  conveys data   |
| Controller <-> Viewer | Controller는 앞서 받은 SaveResult에서 저장한 데이터를 Viewer로 넘겨준 뒤 Viewer는 html 테이블로 출력한다. | provides data |

**3) Extracting the Attributes**

| Concept | Attributes | Attribute Description            |
| ------- | ---------- | -------------------------------- |
| Array   | Array Data  | OCR 결과로 건내 받은 데이터이다. |
|         |            |                                  |
