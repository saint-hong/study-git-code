# git & git hub summary 2..
분산 버전 관리 시스템 "git" 을 git bash를 기반으로 git hub 과 연계하여  유용하게 쓰는 방법들 정리
(윈도우 기반)

## 1.How to use git-github ? 

### 1) git 설치
- git 홈페이지에서 TV 이미지에 있는 다운로드 버튼을 누르면 설치시작.
```
https://git-scm.com
```
- 소스코드로 설치하는 방법도 있다. git-scm 레퍼런스 설명 참조.

### 2) Git 설정
- Git 설치 후 사용 환경을 설정해 두면 업그레이드 해도 설정이 유지된다.
```
$ git config --system : 시스템의 모든 사용자와 저장소에 적용되는 설정
$ git config --global : 현재 사용자에게만 적용되는 설정
$ --local : Git 디렉토리에 있는 특정 저장소에만 적용되는 설정

```
- 사용자 정보 설정 : 사용자 이름과 이메일 주소 설정
- 사용자 정보 설정을 해두면, Git을 통한 commit 작업시 책임자, 권한 설정, 작업자 등의 기록이 남는다.
```
$ git config --global user.name "saint-hong"
$ git config --global user.email "saint-hong@gmail.com"

"--global" 옵션을 빼고 실행하면 프로젝트마다 다른 이름과 이메일 주소 사용 가능
```
- 설정 확인 : 이름, 이메일 등 환경 설정 내용을 확인할 수 있다.
```
$ git config --list
```
### 3) Git 저장소 설정 - 로컬 디렉토리를 저장소로 만들기
- GIt 저장소는 remote 라고 부른다.
- Git 의 remote는  내 컴퓨터의 특정 저장공간으로 지정 할 수도 있고, 웹 서버상의 저장소를 clone 할 수도 있다.
```
① 로컬 디렉토리 하나를 선택해서 Git 저장소를 만든다.
② 또는 웹 서버의 Git 저장소를 clone 한다.
```
- 로컬 디렉토리 저장소 만들기
```
① 특정디렉토리로 이동
$ cd Documents/dev
② .git 폴더 생성 : 저장소에 필요한 뼈대 파일이 생성된다.
$ git init
③ Git 이 파일을 관리하게 하려면 저장소에 어떤 파일을 추가하고 커밋한다.
$ git add test.md
$ git add LICENSE
$ git commit -m "create git"
```

### 4) Git 저장소 설정 - github 의 저장소를 clone 하기
- github 에 만든 repository 의 url 을 clone 하는 방법.
- "git clone" 명령을 사용하면, 해당 주소의 프로젝트 히스토리를 전부 로컬에 받아온다.
```
① 현재 디렉토리에 saint-hong 이라는 디렉토리르 만들고 그 안에 프로젝트를 받아온다.
$ git clone https://github.com/saint-hong/python.git

② url 뒤에 디렉토리 이름을 지정할 수 있다.
$ git clone https://github.com/saint-hong/python.git python_summary
```
- github 과 로컬을 연결할 때 SSH Access 를 설정하면 프로젝트 작업시 비밀번호 등의 인증을 생략할 수 있다.
```
① ssh 디렉토리 이동
$ cd ~/.ssh
② ssh public key 생성하기
$ ssh-keygen -o
③ 생성된 SSH public key 를 복사하기
$ cat ~/.ssh/id_rsa.pub
④ 복사한 퍼블릭 키를 github 에 등록하기
https://github.com/settings/keys -> SSH and GPG keys -> title : git 이름, key : 붙여넣기 -> 저장
```

### 5) Git editor 설정
- Git 에서 프로젝트 실행 시 사용할 기본 편집기를 설정할 수 있다.
- 주로 vim editor 를 많이 사용한다.
```
$ git config --global core.editor "vim"
$ git config --list ### 환경설정 내용 확인
```

### 6) Git 에서 github 사용하기 - basic
- 리모트 레포지토리의 내용을 로컬 레포지토리에 갱신
```
$ git pull <remote>

origin 은 최초 clone 할 때 만들어진 리모트 저장소에 대한 기본 이름이다.
하나의 로컬 디렉토리에 여러개의 리모트 저장소를 등록할 수 있다.
```
- 로컬 레포지토리의 변경 사항을 리모트 레포지토리로 보내기.
```
$ git status ### 로컬 레포지토리의 파일 상태 확인
$ git add <file name>
$ git commit -m "commit msg"
$ git push <remote>
```

#### 참고 : git 사이트의 유용한 레퍼런스 및 웹페이지 참고 (https://git-scm.com/book/en/v2)
