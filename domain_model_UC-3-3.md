# Domain Model for UC-3-3 : 결과출력

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name    |
| ------------------------------------------------------------ | ---- | --------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller      |
| UC-3-2에서 넘겨받은 PolicyData를 가지고 html 테이블 출력한다.              | D   | ShowResult       |
| UC-3-1, UC-3-2에서 사용한 PolicyData의 인스턴스에 결과를 저장한다.   | K    | PolicyData       |


**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| Controller <->  ShowResult      | Controller가 UC-3-1에서 변환한 결과를 제공한다.           | provides data     |

**3) Extracting the Attributes**

| Concept | Attributes | Attribute Description            |
| ------- | ---------- | -------------------------------- |
| Union\[Dict, Array, PolicyDataClass\]   | PolicyData  | 정책 데이터에 대한 표준화 된 클래스이다. |
