# Domain Model for UC-3-1 : DB 업데이트

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name    |
| ------------------------------------------------------------ | ---- | --------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller      |
| 사용자가 복지 정책 csv 파일을 업로드 한다.                      | D    | UploadPolciyFile       |
| 업로드가 성공했으면 csv 파일을 내부적으로 사용할 수 있도록 변환한다.                     | D    | ConvertFile       |
| 내부적으로 변환한 클래스 dict/array/객체 인스턴스이다.               | K    | PolicyData       |
| 변환에 성공했으면 변환한 데이터를 통해 DB를 업데이트 한다.                | D    | UpdatePolicy    |
| 업데이트가 성공적이면 웹에 성공했음을 알림한다.                    | D    | Viewer     |

**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| Controller <-> UploadPolciyFile      | Controller가 유저 입력에 따라 csv 파일을 업로드 한다.             | provides data     |
| UploadPolciyFile <-> ConvertFile | 업로드가 잘되어 서버에 파일이 잘 도착했으면 해당 데이터를 내부적으로 처리하기 편한 데이터로 변환한다                |  converts data   |
| ConvertFile <-> UpdatePolicy | 변환한 데이터를 사용하여 DB를 업데이트하기 위해 변환된 데이터를 넘겨준다.               |  conveys data   |
| Controller <-> Viewer | Controller는 앞서 받은 SaveResult에서 저장한 데이터를 Viewer로 넘겨준 뒤 Viewer는 html 테이블로 출력한다. | provides data |

**3) Extracting the Attributes**

| Concept | Attributes | Attribute Description            |
| ------- | ---------- | -------------------------------- |
| Union\[Dict, Array, PolicyDataClass\]   | PolicyData  | 업로드 된 csv 파일을 변환한 데이터 타입이다 |
