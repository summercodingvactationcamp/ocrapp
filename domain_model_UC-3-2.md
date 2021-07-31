# Domain Model for UC-3-2 : DB 쿼리

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name    |
| ------------------------------------------------------------ | ---- | --------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller      |
| 넘겨받은 OCR 데이터에서 지역과 연령대로 Query한다                    | D    | SearchPolicy       |
| Query한 결과를 객체로 변환하고 시스템에 넘겨줌.                   | D    | ConvertResult       |
| UC-3-1에서 사용한 PolicyData의 인스턴스에 결과를 저장        | K    | PolicyData       |

**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| Controller <-> SearchPolicy      | Controller가 OCR 결과를 넘겨준다           | provides data     |
| SearchPolicy <-> ConvertResult | DB에서 넘겨받은 OCR 결과를 통해 조회한 뒤 결과를 변환하기 위해 넘겨준다.            |  conveys data   |
| ConvertResult <-> Controller | 변환한 결과를 시스템(Controller)에 넘겨준다         |  conveys data   |

**3) Extracting the Attributes**

| Concept | Attributes | Attribute Description            |
| ------- | ---------- | -------------------------------- |
| Union\[Dict, Array, PolicyDataClass\]   | PolicyData  | 정책 데이터에 대한 표준화 된 클래스이다. |
