# Domain Model for UC-xx : ExtractData

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name   |
| ------------------------------------------------------------ | ---- | -------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller     |
| 사용자가 업로드한 사진 파일                                  | K    | Image          |
| OCR 모듈에서 추출한 정보                                     | K    | UserData       |
| OCR 모듈과 데이터를 주고받는 모듈                            | D    | OCR_Connection |
| 사용자에게 올바른 추출인지 검증 여부를 입력받는 변수         | K    | UserInput      |
| 사용자에게 올바른 추출인지 검증 여부를 입력받는 모듈         | D    | GetInput       |
| 이미지에서 민감정보를 가리는 모듈                            | D    | ObscureImage   |
| 이미지와 정보, 혹은 올바르지 않은 형식의 정보인 이유를 출력  | D    | Viewer         |

**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| Controller <-> Image | 이미지는 Controller가 관리한다. (이후 삭제해야하므로) | manages data |
| Controller <-> OCR_Connection | OCR 모듈에 사진파일을 전달한다. | conveys data     |
| OCR_Connection <-> UserData | 추출한 정보를 저장한다. | provides data |
| Controller <-> ObscureImage | 이미지 수정을 명령한다. | requests data |
| ObscureImage <-> Image | Image에서 민감정보를 가린다. | modifies data |
| Controller <-> GetInput | 유저에게 검증 여부를 입력받는다. | requests data |
| GetInput <-> UserInput | 유저가 입력한 검증 여부를 저장한다. | conveys data |
| Controller <-> Viewer | 상황에 맞는 출력을 명령한다. | requests data |


**3) Extracting the Attributes**

| Concept        | Attributes    | Attribute Description                                        |
| -------------- | ------------- | ------------------------------------------------------------ |
| OCR_Connection | Verification  | 추출된 정보가 올바른 정보인지 여부 (UC-xx-VerifyData를 통해 얻어냄) |
|                | InvalidReason | 올바르지 않은 이유                                           |
| ObscureImage   | ObscuredImage | 민감 정보가 가려진 이미지                                    |