## Use Case UC-01: Upload
**1) Related Requirements** : REQ-1, REQ-2

**2) Initiating Actors** : 유저

**3) Actor's Goal** : 유저는 주민등록증 사진을 업로드 할 수 있다. 사진 파일의 형식은 상관없이 올린다.

**4) Participating Actors** : 

**5) Preconditions** :  홈페이지에는 '파일선택' 버튼이 있다. 사진을 올리지 않았을 때는 '선택한 파일이 없음' 문구를 보여준다. 

**6) Postconditions** :  사진을 데이터베이스(클라우드)에 옮긴다. 사진의 파일 형식은 OCR로 분석이 가능한 형태이다.

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                                                 |
| --------- | ---- | ------------------------------------------------------------ |
| →         | 1    | 유저는 '파일 선택'버튼을 누른다.                             |
| →         | 2    | 유저는 자신의 로컬에서 주민등록증 사진을 찾고 확인 버튼을 누른다. |
| ←         | 3    | Viewer는 유저에게 '전송완료'를 보여준다.                     |
