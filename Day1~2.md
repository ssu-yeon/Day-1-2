# TIL(Today I Learned)

## CLI 기초

### [1] GUI와 CLI의 차이

- GUI (Graphic User Interface) : 그래픽을 통해 사용자와 컴퓨터가 상호 작용하는 방식
  - 새로운 폴더 만드는 방식 : 마우스 우클릭 → 새로 만들기 → 폴더 → new 작성
- CLI (Command Line Interface) : 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식
  - 새로운 폴더 만드는 방식 :mkdir new

### [2] 경로

#### (1) 루트, 홈 디렉토리

1. **루트 디렉토리 (Root Directory, `/`)**
   - 모든 파일과 폴더를 담고 있는 최상위 폴더입니다.
   - Windows의 경우 보통은 `C 드라이브`를 의미합니다.
2. **홈 디렉토리 (Home Directory, `~`)**
   - `Tilde(틸드)`라고도 부르며, 현재 로그인 된 사용자의 홈 폴더를 의미합니다.
   - Windows의 경우 `C:/사용자(Users)/현재 사용자 계정`을 의미합니다.
   - Mac의 경우 `/Users/현재 사용자 계정`을 의미합니다.

#### (2) 절대 경로와 상대 경로

1. 절대 경로

    : 루트 디렉토리부터 목적 지점까지 거치는 모든 경로를 전부 작성한 것

   - 윈도우 바탕 화면의 절대 경로 `C:/Users/kyle/Desktop`

2. 상대 경로

    : 현재 작업하고 있는 디렉토리를 기준으로 계산된 상대적 위치를 작성한 것

   - 현재 작업하고 있는 디렉토리가 `C:/Users` 라고 한다면
   - 윈도우 바탕 화면으로의 상대 경로는 `kyle/Desktop` 이 됩니다.
   - 간결해서 좋지만, 현재 작업하고 있는 디렉토리가 변경 되면 상대 경로도 변경됩니다.
   - `./` : 현재 작업하고 있는 폴더를 의미합니다.
   - `../` : 현재 작업하고 있는 폴더의 부모 폴더를 의미합니다.

### [3] 터미널 명령어

* **touch** : 파일을 생성하는 명령어

  ```
  `$ touch text.txt`
  ```

* **mkdir** : 새 폴더를 생성하는 명령어

  ```
  $ mkdir folder
  $ mkdir 'happy hacking'
  ```

  

* **ls** (list segments) : 현재 작업중인 디렉토리의 폴더/파일 목록을 보여주는 명령어

  * -a : all 옵션, 숨김 파일까지 모두 보여줌

  * -l : long 옵션, 용량, 수정날짜 등 파일 정보를 자세히 보여줌

    ```
    # 기본 사용
    $ ls 
    
    # all 옵션
    $ ls -a
    
    # all, long 옵션 함께 적용
    $ ls -a -l
    
    # 여러 옵션 축약 가능
    $ ls -al
    ```

- **mv** (move) : 폴더/파일을 다른 폴더 내로 이동하거나 이름을 변경하는 명령어

  - 단, 다른 폴더로 이동할 때는 작성한 폴더가 반드시 있어야 함. 없다면, 이름이 변경됨

    ```
    # text.txt를 folder 폴더 안에 넣을 때
    $ mv text.txt folder
    
    # text1.txt의 이름을 text2.txt로 바꿀 때
    $ mv text1.txt text2.txt
    ```

- **cd **(change) : 현재 작업 중인 디렉토리를 변경하는 명령어

  - cd ~를 입력하면 홈 디렉토리로 이동

    (cd라고만 입력해도 동일)

  - cd ..를 입력하면 부모 디렉토리로 이동

  - cd -를 입력하면 바로 전 디렉토리로 이동

    ```
    # 현재 작업 중인 디렉토리에 있는 folder 폴더로 이동
    $ cd folder
    
    # 절대 경로를 통한 디렉토리 변경
    $ cd C:/Users/kyle/Desktop
    
    # 상대 경로를 통한 디렉토리 변경
    $ cd ../parent/child
    ```

- **rm** (remove) : 폴더/파일을 지우는 명령어

  - GUI와 달리 휴지통으로 이동하지 않고, 바로 완전 삭제

  > 주의사항 :  *(asterisk, wildcard)를 사용해서 `rm *.txt` 라고 입력하면 txt 파일 전체를 다 지움

  - -r : recursive 옵션. 폴더를 지울 때 사용

    ```
    $ rm test.txt
    $ rm -r folder
    ```

- **start, open** : 폴더/파일을 여는 명령어

  - 윈도우 : start / 맥 : open

    

- **위, 아래 방향키** : 과거에 작성했던 명령어 조회

- **tab** : 폴더/파일 이름 자동 완성

- **ctrl + a** : 커서가 맨 앞으로 이동

- **ctrl + e** : 커서가 맨 뒤로 이동

- **ctrl + w** : 커서가 앞 단어를 삭제

- **ctrl + l** : 터미널 화면을 깨끗하게 청소 (스크롤 올리면 과거 내역 조회 가능)

- **ctrl + insert** : 복사

- **shift + insert** : 붙여넣기

 

## visual studio code

### [1] 기본 터미널 지정

- 터미널 열기

  : 터미널 - new 터미널 또는 ctrl + `(backtick, 백틱)

- powershell > Git Bash로 변경

  -  기존에 떠있는 powershell은 휴지통 버튼을 눌러서 삭제 **(X가 아니라 휴지통)**

    > **X(닫기) 버튼**은 터미널의 내용은 유지하고 잠시 숨겨두는 것
    >
    >**휴지통 버튼**은 터미널을 아예 삭제 하는 것
    >
    >따라서 가독성을 위해 잠시 담고 싶을 때는 X 버튼을 
    >
    >터미널을 삭제하고 싶을 때는 휴지통 버튼을 사용

## Markdown

### [1] Markdown의 정의

- 일반 텍스트 기반의 경량 마크업(Markup) 언어
- 마크업과 반대 개념이 아니라, 마크업을 더 쉽고 간단하게 사용하고자 만들어졌습니다.
- `.md` 확장자를 가지며, 개발과 관련된 많은 문서는 마크다운 형식으로 작성되어 있습니다.
- 개발 분야에 있어서 `문서화`는 굉장히 중요한 능력입니다. 마크다운은 그 토대가 될 것입니다.

### [2] 마크 다운의 장점, 단점, 주의사항

1. 장점
   - 문법이 직관적이고 쉽습니다.
   - 관리가 쉽습니다.
   - 지원 가능한 플랫폼과 프로그램이 다양합니다.
2. 단점
   - 표준이 없어 사용자마다 문법이 상이할 수 있습니다.
   - 모든 HTML 마크업 기능을 대신하지는 못합니다.
3. 주의사항
   - 마크다운의 본질은 글에게 `역할`을 부여하는 것입니다.
   - 따라서 반드시 `역할`에 맞는 마크다운 문법으로만 작성해야 합니다.
   - 예를 들면 `글씨의 크기를 키우고 싶다`는 이유로 `내용`에게 `제목`의 역할을 부여하면 안됩니다. (이 부분은 마크다운 문법을 학습하면서 자연스럽게 이해할 수 있습니다.)

### [3] 마크 문법

#### 1) 제목

- `h1 ~ h6` 에 해당하는 제목을 표현합니다.

- `#`을 사용합니다.

- 작성

  ```markdown
  # 제목 1
  ## 제목 2
  ### 제목 3
  #### 제목 4
  ##### 제목 5
  ###### 제목 6
  ```

#### 2) 강조

- 글자의 스타일링을 표현합니다.

1. **기울임** : `*글자*` 혹은 `_글자_`
2. **굵게** : `**글자**` 혹은 `__글자__`
3. **취소** : `~~글자~~`

#### 3) 코드

- 한 줄 코드인 **인라인 코드**와 여러 줄 코드인 **블록 코드**로 나눌 수 있습니다.

1. 인라인(Inline) 코드 : `inline code`처럼 백틱을 통해 코드를 감싸줍니다.
2. 블록(Block) 코드 : ````python` 처럼 백틱을 3번 입력하고 코드의 종류를 작성합니다.

#### 4) 링크

- 클릭하면 해당 주소로 이동할 수 있는 링크를 표현합니다.
- `[표시할 글자](이동할 주소)` 형태로 작성합니다.

- 작성

  ```markdown
  [GOOGLE](<https://google.com>)을 눌러서 구글로 이동하세요.
  ```

#### 5) 이미지

- 마크다운 문서에 이미지를 삽입할 수 있습니다.

- `![대체 텍스트](이미지 주소)` 형태로 작성합니다.

- `대체 텍스트`란 이미지를 정상적으로 불러오지 못했을 때 표시되는 문구입니다.

- Typora에서는 이미지 파일을 끌어와서 놓아도 자동 업로드 됩니다.

- 작성

  ```markdown
  Git 로고입니다.
  
  ![Git로고](<https://git-scm.com/images/logo@2x.png>)
  ```

#### 6) 인용

- 주석이나 인용 문구를 표현합니다.

- `>` 를 사용합니다. 갯수에 따라 중첩이 가능합니다.

- 작성

  ```markdown
  > 인용문을 작성합니다.
  >> 중첩된 인용문 1
  >>> 중첩된 인용문 2
  >>>> 중첩된 인용문 3
  >>>>> 중첩된 인용문 4
  ```

  

#### 7) 표

- 테이블(표)를 생성합니다.

- `파이프( | )`와 `하이픈( - )`을 이용해서 행과 열을 구분합니다.

- 테이블 양쪽 끝의 `파이프( | )`는 생략 가능합니다.

- 헤더 셀을 구분할 때는 `3개 이상의 하이픈( - )`이 필요합니다.

- Typora에서는 `ctrl + T` 를 통해서 쉽게 표 생성이 가능합니다.

  (Mac은 `option + command + t`)

- 행을 늘릴 때는 `ctrl + enter` 를 누릅니다.

- 작성

  ```markdown
  | 동물   | 종류   | 다리 개수 |
  | ------ | ------ | --------- |
  | 사자   | 포유류 | 4개       |
  | 닭     | 조류   | 2개       |
  | 도마뱀 | 파충류 | 4개       |
  ```

#### 8) 수평선

- 구분 선을 생성합니다.

- `- * _` 을 3번 이상 연속으로 작성합니다.

- 작성

  ```markdown
  ---
  ***
  ___
  ```

## Git 기초

### [1] Git 초기 설정

1. 누가 커밋 기록을 남겼는지 확인할 수 있도록 이름과 이메일을 설정합니다.

   작성자를 수정하고 싶을 때에는 이름, 메일 주소만 다르게 하여 동일하게 입력합니다.

   ```bash
   $ git config --global user.name "이름"
   $ git config --global user.email "메일 주소"
   ```

2. 작성자가 올바르게 설정되었는지 확인 가능합니다.

   ```bash
   $ git config --global -l
   
   또는
   
   $ git config --global --list
   ```

### [2] Git 기본 명령어

#### (0) 로컬 저장소![img](https://hphk.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F7142d992-3d01-481c-9d4e-e818c6e185d8%2FUntitled.png?table=block&id=122e3c54-7fae-4094-a921-ae3c5ac86897&spaceId=daa2d103-3ecd-4519-8c30-4f55e74c7ef4&width=2000&userId=&cache=v2)

- `Working Directory (= Working Tree)` : 사용자의 일반적인 작업이 일어나는 곳

- `Staging Area (= Index)` : 커밋을 위한 파일 및 폴더가 추가되는 곳

- `Repository` : staging area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는 곳

- Git은 **Working Directory → Staging Area → Repository** 의 과정으로 버전 관리를 수행합니다.

#### (1) git init

  ```bash
  $ git init
  Initialized empty Git repository in C:/Users/kyle/git-practice/.git/
  
  kyle@KYLE MINGW64 ~/git-practice (master)
  ```

  - 현재 작업 중인 디렉토리를 Git으로 관리한다는 명령어
  - `.git` 이라는 숨김 폴더를 생성하고, 터미널에는 `(master)`라고 표기됩니다.
  - Mac OS의 경우 `(master)`가 표기되지 않는데, Terminal 업그레이드를 통해 표기할 수 있습니다.

>  <주의사항>
>
>    1. 이미 Git 저장소인 폴더 내에 또 다른 Git 저장소를 만들지 않습니다. (중첩 금지) 즉, 터미널에 이미 (master)가 있다면, git init을 절대 입력하면 안됩니다.
>    2. 절대로 홈 디렉토리에서 git init을 하지 않습니다. 터미널의 경로가 `~` 인지 확인합니다.

  #### (2) git status

  ```bash
  $ git status
  On branch master
  
  No commits yet
  
  nothing to commit (create/copy files and use "git add" to track)
  ```

  - Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어

  - 어떤 작업을 시행하기 전에 수시로 status를 확인하면 좋습니다.

  - 상태

    1. `Untracked` : Git이 관리하지 않는 파일 (한번도 Staging Area에 올라간 적 없는 파일)

    2. ```
       Tracked
       ```

        : Git이 관리하는 파일

       a.`Unmodified` : 최신 상태
       
       b. `Modified` : 수정되었지만 아직 Staging Area에는 반영하지 않은 상태
       
       c. `Staged` : Staging Area에 올라간 상태

    ![img](https://hphk.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F67719520-a1d8-4cbb-81dd-49dea429a7f4%2FUntitled.png?table=block&id=50d78087-1774-48bf-9703-b477d5d579ce&spaceId=daa2d103-3ecd-4519-8c30-4f55e74c7ef4&width=2000&userId=&cache=v2)
    
    파일의 라이프사이클

 #### (3) git **add**

  ```bash
  # 특정 파일
  $ git add a.txt
  
  # 특정 폴더
  $ git add my_folder/
  
  # 현재 디렉토리에 속한 파일/폴더 전부
  $ git add .
  ```

  - Working Directory에 있는 파일을 Staging Area로 올리는 명령어

  - Git이 해당 파일을 추적(관리)할 수 있도록 만듭니다.

  - `Untracked, Modified → Staged` 로 상태를 변경합니다.

    ```bash
    $ touch a.txt b.txt
    
    $ git status
    On branch master
    
    No commits yet
    
    Untracked files: # 트래킹 되고 있지 않는 파일 목록
      (use "git add <file>..." to include in what will be committed)
            a.txt
            b.txt
    
    nothing added to commit but untracked files present (use "git add" to track)
    ```

    ```bash
    # a.txt만 Staging Area에 올립니다.
    
    $ git add a.txt
    ```

    ```bash
    $ git status
    
    On branch master
    
    No commits yet
    
    Changes to be committed: # 커밋 예정인 변경사항(Staging Area)
      (use "git rm --cached <file>..." to unstage)
            new file:   a.txt
    
    Untracked files: # 트래킹 되고 있지 않은 파일
      (use "git add <file>..." to include in what will be committed)
            b.txt
    ```

  #### (4) git **commit**

  ```bash
  $ git commit -m "first commit"
  [master (root-commit) c02659f] first commit
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 a.txt
  ```

  - Staging Area에 올라온 파일의 변경 사항을 하나의 버전(커밋)으로 저장하는 명령어
  - `커밋 메세지`는 현재 변경 사항들을 잘 나타낼 수 있도록 `의미` 있게 작성하는 것을 권장합니다.
  - 각각의 커밋은 `SHA-1` 알고리즘에 의해 반환 된 고유의 해시 값을 ID로 가집니다.
  - `(root-commit)` 은 해당 커밋이 최초의 커밋 일 때만 표시됩니다. 이후 커밋부터는 사라집니다.

  #### (5) **git log**

: 버전들 확인할래!

  ```bash
  $ git log
  commit 1870222981b4731d14ef91d401c68c0bbb2f6e7d (HEAD -> master)
  Author: kyle <kyle123@hphk.kr>
  Date:   Thu Dec 9 15:26:46 2021 +0900
  
      first commit
  ```

  - 커밋의 내역(`ID, 작성자, 시간, 메세지 등`)을 조회할 수 있는 명령어

    - `--oneline` : 한 줄로 축약해서 보여줍니다.

      ```
      $ git log --oneline
      7c69634 (HEAD -> master) first commit- hat equipped
      ```

    - `--graph` : 브랜치와 머지 내역을 그래프로 보여줍니다.

      ```
      $ git log --oneline --graph
      * 7c69634 (HEAD -> master) first commit- hat equipped
      ```

    - `--all` : 현재 브랜치를 포함한 모든 브랜치의 내역을 보여줍니다.

    - `--reverse` : 커밋 내역의 순서를 반대로 보여줍니다. (최신이 가장 아래)

    - `-p` : 파일의 변경 내용도 같이 보여줍니다.

    - `-2` : 원하는 갯수 만큼의 내역을 보여줍니다. (2 말고 임의의 숫자 사용 가능)

💡 **옵션과 인자**


  명령어를 사용하면서 `-` 혹은 `--`를 통해 옵션을 사용하는 것을 배웠습니다. 옵션과 더불어서 인자라는 개념도 존재하는데요. 옵션과 인자 무엇이 다를까요?

  —-

  `옵션`은 명령어의 `동작 방식`을 지정하는 것입니다. 따라서 **생략 가능**합니다. 단순히 기존 기능보다 부가 적인 기능을 원할 때 사용합니다. 예를 들면 `git log --oneline`은 커밋 내역을 한 줄로 보고 싶을 때 사용합니다. `oneline` 옵션은 말 그대로 부가 적인 기능이므로, 생략해도 `git log`는 정상 동작 합니다.

  —-

  `인자`는 명령어의 `동작 대상`을 지정하는 것입니다. 따라서 **생략이 불가능** 합니다. 예를 들면 `git add` 라고만 작성하면 어떤 파일을 Staging Area에 올릴지 모르게 됩니다. 반드시 `git add a.txt` 와 같이 git add 명령어가 동작할 대상을 지정해야 하는데 이때 `a.txt`와 같은 대상을 인자라고 합니다.

  #### (6) 한눈에 보는 Git 명령어

  ![img](https://hphk.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fc86c667a-616f-45b6-892e-15da6a3c494e%2FUntitled.png?table=block&id=2e56021a-5b15-4d21-b36e-4b3b0f3a1eb8&spaceId=daa2d103-3ecd-4519-8c30-4f55e74c7ef4&width=2000&userId=&cache=v2)

#### (7) **그 외 명령어**

- git config --global --list

  ```
  user.email=a46448489@gmail.com
  user.name=ssu-yeon
  ```

#### (8) **git checkout**

- 돌아가보기

  : git checkout 해쉬 (예를 들어, c23a3a8) 

  ```
  $ git checkout c23a3a8
  Note: switching to 'c23a3a8'.
  
  You are in 'detached HEAD' state. You can look around, make experimental
  changes and commit them, and you can discard any commits you make in this
  state without impacting any branches by switching back to a branch.
  
  If you want to create a new branch to retain commits you create, you may
  do so (now or later) by using -c with the switch command. Example:
  
    git switch -c <new-branch-name>
  
  Or undo this operation with:
  
    git switch -
  
  Turn off this advice by setting config variable advice.detachedHead to false
  
  HEAD is now at c23a3a8 fourth commit -glass
  ```

  : git checkout head~숫자

  ```
  $ git checkout head~3
  Note: switching to 'head~3'.
  
  You are in 'detached HEAD' state. You can look around, make experimental
  changes and commit them, and you can discard any commits you make in this
  state without impacting any branches by switching back to a branch.
  
  If you want to create a new branch to retain commits you create, you may
  do so (now or later) by using -c with the switch command. Example:
  
    git switch -c <new-branch-name>
  
  Or undo this operation with:
  
    git switch -
  
  Turn off this advice by setting config variable advice.detachedHead to false
  
  HEAD is now at f1103ba second commit -glove
  ```

  

- 다시 나오기

  : git checkout master

  ```
  user@DESKTOP-GB00T4T MINGW64 ~/test ((f1103ba...))
  $ git checkout master
  Previous HEAD position was f1103ba second commit -glove
  Switched to branch 'master'
  
  user@DESKTOP-GB00T4T MINGW64 ~/test (master)
  ```


#### (9) git remote add origin 주소

: 브릿지 잇기

- 이어진 거 확인 : git remote -v

#### (10) git push origin master

: 올리기!

#### (11) .gitignore

> 특정 파일 혹은 폴더에 대해 Git이 버전 관리를 하지 못하도록 지정하는 것

##### (1) .gitignore에 작성하는 목록

- 민감한 개인 정보가 담긴 파일 (전화번호, 계좌번호, 각종 비밀번호, API KEY 등)
- OS(운영체제)에서 활용되는 파일
- IDE(통합 개발 환경 - pycharm) 혹은 Text editor(vscode) 등에서 활용되는 파일
  - 예) pycharm -> .idea/
- 개발 언어(python) 혹은 프레임워크(django)에서 사용되는 파일
  - 가상 환경 : `venv/`
  - `__pycache__/`

##### (2) .gitignore 작성 시 주의 사항

- 반드시 이름을 `.gitignore`로 작성합니다. 앞의 점(.)은 숨김 파일이라는 뜻입니다.

- `.gitignore` 파일은 `.git` 폴더와 동일한 위치에 생성합니다.

- **제외 하고 싶은 파일은 반드시 `git add` 전에 `.gitignore`에 작성합니다.**

  ❗ **왜 git add 전에 .gitignore에 작성해야 할까요?**

  `git add a.txt` 라고 작성하면, 이제 Git은 `a.txt`를 버전 관리의 대상으로 여깁니다. 한 번 버전 관리의 대상이 된 `a.txt`는 이후에 .gitignore에 작성하더라도 무시되지 않고 계속 버전 관리의 대상으로 인식됩니다. 따라서 제외 하고 싶은 파일은 반드시 git add 전에 .gitignore에 작성해야 합니다!

#### (12) clone, pull

> 지금까지는 로컬 저장소의 내용을 원격 저장소에 업로드하는 것을 학습했습니다. 
>
> 이번에는 반대로, 원격 저장소의 내용을 로컬 저장소로 가져오는 것을 학습합니다.

##### (1) git clone

- 원격 저장소의 커밋 내역을 모두 가져와서, 로컬 저장소를 생성하는 명령어

- clone은 `"복제"`라는 뜻으로, `git clone` 명령어를 사용하면 원격 저장소를 통째로 복제해서 내 컴퓨터에 옮길 수 있습니다.

- `git clone <원격 저장소 주소>`의 형태로 작성합니다.

  ```bash
  $ git clone <https://github.com/edukyle/TIL.git>
  Cloning into 'TIL'...
  remote: Enumerating objects: 3, done.
  remote: Counting objects: 100% (3/3), done.
  remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
  Receiving objects: 100% (3/3), done.
  ```

  위에 작성한 대로 실행하면, `Github의 edukyle이라는 계정의 TIL 원격 저장소를 복제`하여 내 컴퓨터에 TIL이라는 이름의 로컬 저장소를 생성하게 됩니다.

- git clone을 통해 생성된 로컬 저장소는 `git init`과 `git remote add`가 이미 수행되어 있습니다.

##### (2) git pull

- 원격 저장소의 변경 사항을 가져와서, 로컬 저장소를 업데이트하는 명령어

- 로컬 저장소와 원격 저장소의 내용이 완전 일치하면 git pull을 해도 변화가 일어나지 않습니다.

- `git pull <저장소 이름> <브랜치 이름>`의 형태로 작성합니다.

  ```bash
  $ git pull origin master
  From <https://github.com/edukyle/git-practice>
   * branch            master     -> FETCH_HEAD
  Updating 6570ecb..56809a9
  Fast-forward
   README.md | 1 +
   1 file changed, 1 insertion(+)
  
  [풀이]
  git 명령어를 사용할건데, origin이라는 원격 저장소의 master 브랜치의 내용을 가져온다(pull).
  ```

💡 **git clone vs git pull**

clone과 pull이 모두 원격 저장소로부터 가져오는 명령어라서 조금 혼동될 수 있습니다.

`git clone`은 git init처럼 처음에 한 번만 실행합니다. 즉 로컬 저장소를 만드는 역할이죠. 단, git init처럼 직접 로컬 저장소를 만드는 게 아니라, Github에서 저장소를 복제해서 내 컴퓨터에 똑같은 복제본을 만든다는 차이가 있습니다.

`git pull`은 git push처럼 로컬 저장소와 원격 저장소의 내용을 동기화하고 싶다면 언제든 사용합니다. 단, push는 로컬 저장소의 변경 내용을 원격 저장소에 반영하는 것이고, pull은 원격 저장소의 변경 내용을 로컬 저장소에 반영하는 것입니다. **즉 방향이 다릅니다!**
