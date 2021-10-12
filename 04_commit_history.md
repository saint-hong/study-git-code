# commit 실행 기록을 확인하고 관리하는 방법
- git 의 commit 히스토리 확인 / 동료가 무엇을 커밋했는지 리뷰하고 빨리 조회할 수 있다. 

### 방법
- commit 요약 정보 확인
- 어떤 아이디가 commit 했는지 확인할 수 있다
```
$ git log : 체크섬, 이름, 이메일, 수정 날짜, 수정 이름
$ git log -p -2 : 커밋의 diff 결과 확인,  -2 는 2개만 확인
$ git log --stat : 히스토리의 통계 정보 조회, 몇줄, 몇개가 수정됐는지 요약해서 보여줌 / 유용하다
```

- commit 히스토리를 여러가지 방법으로 조회 가능
```
$ git log --pretty=oneline : 커밋의 체크섬과 커밋 이름을 한줄로 요약해서 보여줌.
$ git log --pretty=format: "%an %ae" : 저자이름과 저자메일만 출력 / 옵션 여러가지 있음 -> format 으로 출력하면 많은 커밋의
출력 내용을 통일하고 다른 프로그램으로 파싱할 때 좋음
$ git log --pretty=format:"%an %cn" : 저자이름과 커미터 이름을 출력
- 저자author 와 커미터committer : 저자는 원래 작업을 수행한 사람, 커미터는 마지막으로 커밋 한 사람. 프로젝트 진행하다
보면 저자와 커미터가 다를 수 있다.
$ git log --pretty=format: "%H %h %an %cn" --graph : 브랜치와 머지 히스토리를 아스키 그래프로 출력해준다. --graph

```

- commit 히스토리가 많을 경우 제한 조건을 사용하여 원하는 것을 조회할 수 있다.
- 옵션 여러가지 있음
```
$ git log --since=2.weeks : 지난 2주동안 만들어진 커밋들만 조회
$ git log -S function_name :  코드에서 추가, 수정 된 내용에 포함되어 있는 것을 특정하여 조회.
```






