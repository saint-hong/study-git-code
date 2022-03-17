# git hub 저장소와 연결된 디렉토리 삭제
- git hub에서 새로운 레포지토리를 생성하고 컴퓨터에 git clone 을 하면 해당 저장소 remote의 이름으로 새로운 디렉토리가 생성된다.
- 이 과정에서 로컬(내 컴퓨터)에 새 저장소가 생기고 이 저장소는 git hub의 새 레포지토리 저장소와 연결이 된다.
- 그런데 간혹 이렇게 생성된 내 컴퓨터의 디렉토리를 삭제해야 할 경우가 있다. 
- 삭제를 하려고 rm [새폴더] 명령어를 사용해도 완저히 삭제되지 않는다.
   - 그 이유는 git clone을 해서 새로운 저장소를 만들때 숨김파일 등이 같이 생성되고, 이 파일들이 rm 명령어로 완전히 삭제되지 않기 때문이다.

### 삭제 방법
- 삭제하려고 하는 워킽 디렉도리의 remote 를 확인한다.
   - git hub의 저장소와 연결될때 설정한 연결 이름이 뜬다.
   - 따로 변경을 안했으면 origin 이 remote의 이름이다.
```python
git remote 
>>> remote의 이름이 나온다.

git remote -v 
>>> 저장소의 주소가 나온다.
```

- 브랜치 확인
   - 중요 내용은 없는지, 브랜치에 아직 처리되지 않은 commit이 있는지 확인한다.
```python
git branch
```

- commit 로그 기록 확인
   - commit이 내가 한 작업인지, 다른 사람이 한 작업인지 등을 파악 할 필요가 있다.
   - commit 작업자 명이 내이름이 어도 작업 프로세스에 따라서 삭제하면 안될 수도 있다.
```python
git log --pretty==oneline 

>>> commit 기록 확인

74c32667a855154ca6d3e2d6fd7baf016c09cea3 git_hub_summary
bf2bb6165d2fc297df79d23813a9aa5ba393707a Merge branch 'master' of https://github.com/saint-hong/git-code
5b27fb091bb513184544740be76036ff62ddaef9 git_hub_summary
646a55f8d086837b9a24eaed765a69f03976a6ae Update README.md
692c91069cc5b42936c285dc99e20bf74dfb097b Update code_summary.md
```

- 현재 저장소의 git 상태 확인
```python
git status

>>> 현재 진행중인 단계의 정보가 나온다. 

git status -s

>>> 현재 진행중인 작업 단계의 요약정보가 나온다. (워킹 단계의 약자가 떠서 확인하기 편하다)
```

- remote 이름을 확인 후 삭제하려는 디렉토리에서 이 remote를 삭제한다.
   - origin remote가 삭제된다.
   - 즉 레포지토리와 디렉토리의 연결이 끊어진다.
```python
git remote remove <remote 이름>
```

- 현재 디렉토리의 모든 하위 파일 삭제
```python
rm rf *
```

- 숨김 폴더 삭제
```python
rm rf .git 

>>> .git 디렉토리 삭제된다. 숨김 폴더
```

- 강제 옵션을 추가하여 디렉토리 삭제
   - 디렉토리 안에 파일이 있어도 삭제된다.
```python
rm -rf <파일 또는 디렉토리 이름>
```

- 추가
   - 디렉토리가 비워지지 않아도 디렉토리를 삭제할 수 있는 명령어
```python
rmdir --ignore-fail-on-non-empty <디렉토리 명>
```

### 레포지토리와 워킹 디렉토리의 삭제는 신중하게 해야한다.



