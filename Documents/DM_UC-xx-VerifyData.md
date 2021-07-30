# Domain Model for UC-xx : VerifyData

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name  |
| ------------------------------------------------------------ | ---- | ------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller    |
| OCR 모듈에서 추출한 정보                                     | K    | UserData      |
| 올바른 형식으로 된 정보인지의 여부                           | K    | Verification  |
| UserData를 검증하는 모듈                                     | D    | Verifier      |

**2) Extracting the Associations**

| Concept pair              | Association Description | Association Name |
| ------------------------- | ----------------------- | ---------------- |
| Controller <-> Verifier   | 정보 검증을 요청한다.   | requests data    |
| Verifier <-> Verification | 검증 여부를 저장한다.   | conveys data     |
| Verifier <-> UserData     | UserData를 검증한다.    | verifies data    |

**3) Extracting the Attributes**

| Concept      | Attributes    | Attribute Description                                        |
| ------------ | ------------- | ------------------------------------------------------------ |
| Verifier     | InvalidReason  | 올바르지 않은 이유 |