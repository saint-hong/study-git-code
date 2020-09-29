# git code summary..
  자주 사용하지만, 자주 잊어버리는 코드들 정리

## 1. basic

### 1) path move
```
$ cd <dir name> : <dir name> 으로 이동
$ cd /c/<dir name> : 절대경로 /c/<dir name> 으로 이동
$ cd . : 현재 디렉토리
$ cd .. : 상위 디렉토리 이동
$ cd ../../ : 두번쨰 상위 디렉토리 이동
```

### 2) confirm
```
$ pwd : 현재 위치 확인
$ ls : 현재 디렉토리 안의 디렉토리와 파일을 확인
$ ls -al : 현재 디렉토리 안의 디렉토리와 파일의 chmod, 생성일시 등의 정보를 확인
	   (숨겨진 파일, 폴더도 확인 가능)
```

### 3) clear
```
$ clear : git bash의 현재 화면의 내용 지우기
```

### 4) history
```
$ history : 현재까지 실행한 code의 history를 확인
$ !20 : history 중 20번째의 code를 실행
$ echo $HISTFILE :  history file의 경로 확인. history file 을 삭제가능
```

### 5) genesis
```
$ mkdir test : 현재 위치에서 test 디렉토리 생성
$ mkdir test/t1/t2 : 현재 위치에서 하위구조로 생성 test > t1 > t2 
$ mkdir test/(a,b,c) : test 디렉토리를 만들고 하위에 각각 a, b, c 디렉토리 생성
$ touch test.txt : 현재 위치에서 test.txt 파일 생성
```

### 6) copy 
```
$ cp test.txt test_2.txt : test.txt 파일의 복사본 test_2.txt 생성 (이름 변경 가능)
$ cp test.txt abc/ : test.txt 파일을 같은 위치의 abc 디렉토리에 복사본 생성
$ cp test.txt ../apple/test_copy.txt : test.txt 파일을 상위 경로의 apple 디렉토리에 test_copy.txt
				      이름으로 복사본 생성
$ cp -r test test2 : 현재 위치의 test 디렉토리를 test2 이름으로 복사본 생성
$ cp <origin file> <path>/<path>/<dir name>/<dir name>/<copy name>
```

### 7) delete
```
$ rm test.txt : test.txt 파일 삭제
$ rmdir test : test 디렉토리 삭제
$ rm -r test : rm 명령어 사용시 -r, -rf 옵션 사용 가능 (-r 삭제, -f 강제)
$ rm -rf a* : 현재 디렉토리에서 a로 시작하는 파일 모두 삭제
$ rm -rf *.txt : 현재 디렉토리에서 .txt 파일 모두 삭제
$ rm -rf <file name> 또는 <dir name> : 파일, 디렉토리 삭제
$ rmdir --ignore-fail-on-non-empty <dir name> : 디렉토리 안에 파일이 들어있어도 무시하고 삭제
$ rm --help : rm 명령어에 관한 tip 확인
```

### 8) cut & paste = move
```
$ mv aaa.txt bbb.txt : aaa.txt 파일을 bbb.txt 파일로 이름을 바꾸기
$ mv test.txt ./t1/t2/test_2.txt : test.txt 파일을 t1 > t2 디렉토리로 test_2.txt 로 이름바꿔서 이동
```

### 9) search file
```
$ head -3 test.txt : test.txt 파일의 위에서부터 3번째 라인까지 출력
$ tail -3 test.txt : test.txt 파일의 밑에서부터 3번째 라인까지 출력
$ head -3 ../test/aaa/bbb/test.txt :  상위 경로의 test > aaa > bbb 디렉토리의 test.txt 파일의 위에서 					3번쨰 라인까지 출력
$ head -n 10 <file name> | tail -n 5 : 위에서 10번째 라인 중에서 아래에서 5번째 라인까지 출력
$ tail -n 10 <file name> | head -n 5 : 아래에서 10번째 라인 중에서 위에서 5번째 라인까지 출력
```

## 2. apply

### 1) using jupyter notebook
```
$ jupyter notebook : 현재 디렉토리에서 jupyter notebook 접속
$ ctrl + c : jupyter notebook 접속 종료

<ubuntu server 에서 접속시>
$ jupyter notebook & : 백그라운드에서 jupyter notebook 실행, bash shell 사용 가능
$ ps -e | grep note : jupyter notebook 의 process id 확인
$ kill -9 12345 : 백그라운드에서 실행된process id 종료, jupyter notebook 접속 종료
```

### 2) chmod
```

```




















