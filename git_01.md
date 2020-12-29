# git 기초

> 분산버전 관리시스템(DVCS)

## 0. 로컬 저장소(repository) 설정

```bash
$ git init
Initialized empty Git repository in C:/Users/USER/Desktop/practice/.git/

```



* .git 폴더가 생성되고, 여기에 모든 git과 관련된 정보들이 저장된다.

## 기본 작업 흐름

> 모든 작업은 touch 로 파일을 만드는것으로 대체

### 1.add

```bash
$ git add. # . : 현재 디렉토리(하위 디릭토리 포함)
$ git add a.txt # 특정파일
$ git add my_folder/ # 특정폴더

```

* 커밋의 대상 파일을 관리한다.

  ```bash
  $ touch a.txt
  $ git status
  On branch master
  
  No commits yet
  # 트레킹이 되고 있지 않는 파일들..
  # => 새로 생성된 파일
  Untracked files:
  	# add 명령을 사용해
  	# 커밋이 될 것에 포함시키기 위하여..
  	# => staging Area (두번째통)
    (use "git add <file>..." to include in what will be committed)
          a.txt
  
  nothing added to commit but untracked files present (use "git add" to track)
  ```

  

* add 이후

  ```bash
  $ git add .
  $ git status
  On branch master
  
  No commits yet
  # 커밋이 될 변경사항
  # SA 두번째통에 있는 애들..
  Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
          new file:   a.txt
  ```

  

### 2. commit

```bash
$ git commit -m 'First commit'
[master (root-commit) eb29d86] First commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```

* commit 은 지금 상태를 스냅샷을 찍는다 라고 표현.
* commit -m은 지금 가록하는 이력을 충분히 잘 나타낼 수 있도록 작성.
* git log 명령어를 통해 지금까지 기록된 커밋들을 확인할 수 있다.

## 기타명령어

### 1. status

```bash
$ git status
```

 ### 2. log

``` bash
$ git log
commit eb29d864c1cbf6e881db4fc4f85d818c5e7ee049 (HEAD -> master)
Author: leonid36 <ljws94@gmail.com>
Date:   Tue Dec 29 14:11:02 2020 +0900

    First commit
    
$ git log --oneline
eb29d86 (HEAD -> master) First commit
$ git log -2
$ git log --oneline -1
```

# git commit author 설정

최초에 컴퓨터에서 git을 활용하려고 하면, 아래의 설정을 하지 않으면 commit이 안된다.

```bash
$ git config --global user.name __username__
$ git config --global user.email __useremail__

```

* 



# 실습 1. TIL 첫번째 커밋하기

## 준비사항

* TIL 폴더
* (선택) 기존에 정리한 마크다운 파일 다 넣기

## 단계

* git 로컬 저장소로 TIL 폴더를 지정

* 첫 번째 커밋을 남기기

  ​	* (심화) 마크다운 파일이랑 git파일이랑 따로 커밋

