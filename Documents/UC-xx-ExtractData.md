## Use Case UC-xx: ExtractData
**1) Related Requirements** : REQ-4, REQ-5, REQ-6

**2) Initiating Actors** : system(임시)  or 유저?

**3) Actor's Goal** : 사진 파일에서 성명, 나이, 지역 정보를 읽어 추출한다.

**4) Participating Actors** : OCR-module

**5) Preconditions** :  

**6) Postconditions** : 사진 파일은 삭제된다. 시스템에 추출한 정보를 전달한다.  

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                                                 |
| --------- | ---- | ------------------------------------------------------------ |
| →         | 1    | OCR module에 전달된 사진에서 정보를 추출한다.                |
|           | 2    | include UC-xx-VerifyData                                     |
| ←         | 3    | 추출된 정보를 민감 정보가 가려진 사진과 함께 띄워 유저에게 검증받는다. |
| →         | 4    | 정보가 잘 추출되었는지 여부를 입력받는다.                    |
| ←         | 5    | 시스템에 추출한 정보를 전달한다.                             |

**8) Flow of Events for Extensions (Alternate Scenarios)**

2a. 추출된 정보가 올바르지 않은 형식일 경우

| Direction | n    | Actor Action                                        |
| --------- | ---- | --------------------------------------------------- |
| ←         | 1    | 추출된 정보가 올바르지 않은 형식인 이유를 출력한다. |
| →         | 2    | 확인 버튼이 입력된다.                               |
|           | 3    | include UC-01-Upload                                |



4a. 추출된 정보가 올바르지 않다고 유저가 입력했을 경우
| Direction | n    | Actor Action         |
| --------- | ---- | -------------------- |
|           | 1    | include UC-01-Upload |
