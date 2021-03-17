# git 기초

> 분산버전관리시스템(DVCS)

## 로컬 저장소(repository) 설정

```bash
$ git init
Initialized empty Git repository in C:/Users/user/OneDrive/문서/인공지능/인공지능앱/깃_깃헙수업/Tyr/.git/

(master) $

```

* `.git` 폴더가 생성되고, 여기에 git과 관련된 모든 정보들이 저장된다.

## 기본 작업 흐름

모든 작업은 `touch` 명령어를 통해서 파일을 만드는 것으로 대체

### 1. `add`

```bash
$ git add __디렉토리__
$ git add a.txt # 특정 파일
$ git add myfolder # 특정 폴더
$ git add a.txt b.txt # 특정 파일들
$ git add . # 현재 디첵토리(하위 디렉토리 포함)
```

* 커밋 대상 파일 목록에 추가한다.
  * working directory의 변경사항(첫번째통)을 staging area(두번째통) 상태로 변경시킨다.

#### add 이전

```bash
$ touch new.txt
$ git status
On branch master
Untracked files:
  # 커밋이 될 것에 포함시키기 위해서는 git add 명령어를 사용..
  # => 두번째통(staging area)에 담기 위해서..
  (use "git add <file>..." to include in what will be committed)
  # 파일 목록
        new.txt

# SA X,
# WD O
nothing added to commit but untracked files present (use "git add" to track)
```

#### add 이후

```bash
$ git add .
$ git status
On branch master
Changes to be committed:
# 변경사항들.. 커밋될
# Staging area O
  (use "git restore --staged <file>..." to unstage)
        new file:   new.txt

```

### 2. `commit`

```bash
$ git commit -m 'Add new.txt'
[master 00aae9d] Add new.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.txt
```

* `commit` 지금 파일 상태를 스냅샷
* 커밋 메시지는 코드 변경사항(이력/버전/커밋)를 충분히 잘 나타냇 수 있도록 작성한다.
* 아래의 명령어를 통해서 지금까지 기록된 커밋을 확인할 수 있다.



### log

```bash
$ git log
commit 00aae9d9cec89b8392a4ba68cd4fd4a1ee7170db (HEAD -> master)
Author: Seunggyeom Kim <fxf24@naver.com>
Date:   Tue Mar 16 15:08:17 2021 +0900

    Add new.txt

commit 8669e3651131183c0ad53ba983022272f93238be
Author: Seunggyeom Kim <fxf24@naver.com>
Date:   Tue Mar 16 15:02:56 2021 +0900

    first commit

$ git log --oneline
00aae9d (HEAD -> master) Add new.txt
8669e36 first commit

$ git log --1
commit 00aae9d9cec89b8392a4ba68cd4fd4a1ee7170db (HEAD -> master)
Author: Seunggyeom Kim <fxf24@naver.com>
Date:   Tue Mar 16 15:08:17 2021 +0900

    Add new.txt

$ git log  --oneline -1
00aae9d (HEAD -> master) Add new.txt

```



