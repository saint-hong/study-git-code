# git & git hub summary 1..
분산 버전 관리 시스템 "git" 을 git bash를 기반으로 git hub 과 연계하여  유용하게 쓰는 방법들 정리

## 1. what is git?

### 1) 개념   
- DVCS : 
```
Distributed version control system, 분산 버전 관리 시스템
```
- 버전관리시스템의 최신 형태
- 서버와 로컬에서 파일의 버전을 효율적으로 관리(히스토리, 저장, 수정, 업데이트 등)할 수 있는 시스템
```
VCS -> CVCS -> DVCS
```
- 장점 
```
"빠른속도, 단순한 구조, 비선형적인 개발(수천개의 동시 다발적 브랜치), 완벽한 분산, 대형프로젝트에도 유용하게 사용가능"
```
### 2) 기능
```
① server computer 와 local computer 의 다대다 관계에서 송수신 가능
② s.c 와 l.c 각각에 파일의 버전을 저장하여 관리할 수 있다.
③ s.c 가 연결이 되지 않더라도 l.c 에 저장되어 있는 파일로 작업을 할 수 있다.
④ s.c 와 l.c 의 저장되어 있는 파일의 버전을 쉽게 비교하여 조정할 수 있다.
⑤ 최초의 버전과 수정된 버전의 충돌에 구애받지 않고, 여러 l.c 가 함께 작업을 할 수 있다.
```
### 3) 원리
- snap shot
```
① git 이 데이터를 관리하는 방법으로 프로젝트의 버전이 바뀌는 시간순으로 스냅샷을 저장하는 방식이다.
② 프로젝트의 버전이 변경되어 새로 저장되는 순간마 다, 전체 파일을 저장하는데 버전이 바뀌지 않은 파일은 새로 저장하지 않고 이전 상태의 링크만 저장한다. 
③ 다른 VCS 프로그램들은 데이터를 파일의 목록으로 관리하고, 버전이 바뀌는 파일들만 시간순으로 관리한다. 
```
- checksum
```
① git 에서 사용하는 가장 기본적인 데이터 단위. 
② SHA-1 해시를 사용하여 체크섬을 만들고 40자 길이의 16 진수 문자열로 만들어진다. 
③ git 은 모든 것을 이 체크섬으로 식별한다.
```
- git directory (repository)
```
① 프로젝트의 메타데이터와 데이터베이스를 저장하는 곳. 
② 다른 컴퓨터, 서버의 저장소를 Clone 할 때 git directory가 생성된다. HEAD 라고 부르기도 함.
```
- working directory
```
① 워킹트리, 프로젝트의 특정 버전을 checkout 한 것. 
② git direcotry에 저장된 데이터베이스에서 파일을 가져와서 워킹 트리를 만든다. 
```
- staging area
```
① 단순한 파일형태로 커밋할 파일에 대한 정보를 저장함. 
② git directory 안에 있다. index 라고도 한다.
```
- Modified
```
파일을 수정했지만 아직 로컬 데이터베이스에 커밋하지 않은 것.
```
- staged
```
수정한 파일을 곧 커밋할 것이라고 표시한 상태.
```
- committed
```
데이터가 로컬 데이터베이스에 안전하게 저장된 상태.
```
### 4) 과정
```
① checkout 한 파일을 워킹 트리에서 수정 후 staging area 에 추가, staged 상태.
② 수정은 했지만 staging area 에 추가안 한 것은 modified 상태.
③ staging area 에 파일을 stage 해서 커밋할 스냅샷 구성.
④ staging area 에 있는 파일들을 커밋해서 git directory에 영구적인 스냅샷으로 저장.
⑤ (checkout) working tree -> modified -> (staged) staging area -> (committed) git directory -> (checkout) working tree -> repeat
```
### Git Areas
![areas](../Image/areas.png)

#### 참고 : git 사이트의 유용한 레퍼런스 및 웹페이지 참고 (https://git-scm.com/book/en/v2)



