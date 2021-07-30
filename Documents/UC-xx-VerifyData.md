## Use Case UC-xx: VerifyData
**1) Related Requirements** : REQ-7, REQ-8, REQ-9

**2) Initiating Actors** : OCR-Module

**3) Actor's Goal** : 추출한 정보가 올바른 형식인지 검증한다.

**4) Participating Actors** : 

**5) Preconditions** :  OCR-Module에서 사진 파일을 읽어 정보가 추출된 상태여야 한다.

**6) Postconditions** :  

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                          |
| --------- | ---- | ------------------------------------- |
| →         | 1    | 추출된 정보를 검증한다.               |
| ←         | 2    | 추출된 정보가 올바른 형식임을 알린다. |

**8) Flow of Events for Extensions (Alternate Scenarios)**

1a. 추출된 정보가 올바르지 않은 형식일 경우

| Direction | n    | Actor Action                                 |
| --------- | ---- | -------------------------------------------- |
| ←         | 1    | 추출한 정보가 올바르지 않은 이유를 전달한다. |