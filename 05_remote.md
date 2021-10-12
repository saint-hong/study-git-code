# remote 관리와 사용방법들
- remote는 저장소라고 부른다.
- remote는 git hub의 레포지토리와 로컬 컴퓨터를 연결해주는 기능을 한다.
- romote는 로컬 컴퓨터 자체에다가 만들 수도 있다.
- 파일의 수정, 생성, 삭제 등 변경사항이 최종적으로 보관되는 공간

### 방법
- remote 생성, 삭제 등 기본적인 사용방법
```
$ git remote : 리모트 저장소의 목록 확인 (최초 리모트 저장소 연결 하면 origin 이라는 이름으로 생긴다.)
$ git remote -v : 리모트 저장소의 주소
$ git remote remove <remote name> : 리모트 삭제
$ git remote add <이름> <저장소 url> :  리모트 저장소를 추가한다. 이름은 origin 말고 어떤 이름도 가능

<예시>
git remote remove origin : origin 저장소 삭제
git remote -v : 리모트 저장소의 주소 확인 (위에서 삭제했으므로 아무것도 안나옴)
git remote add origin https://github.com/saint-hong/study-python : origin 저장소 생성하고 주소를 붙여준다.

$ git remote show origin : 리모트 저장소의 구체적인 정보 확인. master 브랜치와 merge 할 브랜치가 어떤것인지도 확인가능.

```

- remote 의 데이터를 가져오는 방법들
- fetch 와 pull 의 기능
```
$ git fetch origin : origin 리모트 저장소의 데이터를 모두 로컬로 가져온다. merge 는 수동으로 해줘야 한다.
$ git pull origin : 리모트 저장소의 브랜치 데이터를 가져오고, 자동으로 merge 까지 한다.
$ git clone <url> : clone 은 로컬의 master 브랜치가 리모트 저장소의 master 브랜치를 추적하도록 한다.
```

### tip
- 일반적으로 git hub 에서 레포지토리를 생성 -> 레포지토리 url 복사 -> git clone <url>
- 레포지토리가 remote가되고 내 컴퓨터에 레포지토리의 이름과 같은 디렉토리가 생성된다.
- 내 컴퓨터에 생성된 디렉토리와 remote 와 연결되고, 레포지토리의 데이터를 가져오게 된다.

