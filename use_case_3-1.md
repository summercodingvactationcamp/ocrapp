## Use Case UC-3-1: Update DB

**1) Related Requirements** : REQ-10, REQ-11

**2) Initiating Actors** : User(Admin)

**3) Actor's Goal** : 지역구 별 연령별 복지정책을 업데이트 한다

**4) Participating Actors** : Viewer, DB

**5) Preconditions** :  None

**6) Postconditions** :  None

**7) Flow of Events for Main Success Scenario**
| Direction | n    | Actor Action                          |
| --------- | ---- | ------------------------------------- |
| →         | 1    | Admin이 연령, 지역구가 모두 합쳐진 csv 파일을 업로드 한다               |
|          | 2    | 업로드한 파일을 csv 파일을 DB에 업데이트 한다. |
|  ←       | 4    | 성공적으로 업데이트 했음을 웹에 알림창으로 띄운다 |

**8) Flow of Events for Extensions (Alternate Scenarios)**

a. 업로드한 csv 파일이 올바르지 않은 형식일 경우

| Direction | n    | Actor Action                                 |
| --------- | ---- | -------------------------------------------- |
| ←         | 1    | 잘못된 형식임을 알린다 |
