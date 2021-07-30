# Domain Model for UC-01 : Upload 

**1) Extracting the Responsibilities**

| Responsibility Description                                   | Type | Concept Name    |
| ------------------------------------------------------------ | ---- | --------------- |
| UseCase, UseCase의 논리적 집합 혹은 전체 시스템과 관련된 작업을 조정하고 다른 concept에 위임한다. | D    | Controller      |
| 사용자가 업로드한 신분증 이미지 파일                         | K    | Image           |
| 파일 업로드 상태에 대해 보여준다.                            | D    | Viewer          |
| 이미지를 입력받는다.                                         | D    | ImageGetter     |
| 이미지를 입력받아 저장하는 모듈                              | D    | ImageField      |
| 클라우드서버와 커넥트하는 모듈                               | D    | CloudConnection |



**2) Extracting the Associations**

| Concept pair | Association Description | Association Name |
| ------------------ | ----------------------- | ---------------- |
| ImageGetter <-> Controller     | Image가  Controller에 전달이 된다.                       | conveys data     |
| Controller <-> ImageField      | Controller가 Image를 ImageField에 전달한다.              | conveys data     |
| ImageField <-> CloudConnection | Image를 클라우드 서버에 전달해 저장한다.                 | provides data    |
| Controller <-> Viewer | Controller는 표시할 파일 전송상태를 Viewer에게 전달한다. | provides data |

**3) Extracting the Attributes**

| Concept | Attributes | Attribute Description            |
| ------- | ---------- | -------------------------------- |
| Image   | ImageInfo  | 사용자가 입력한 이미지 파일이다. |
|         |            |                                  |