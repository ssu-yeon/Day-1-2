# **깃허브**

## **깃 명령어 정리** 

1. -mkdir => 폴더 만듦 

2. touch a.txt -> 파일 

3. git init -> 관리시작! 

4. ls -a : 숨김 보기 

5. git status : 현황! 

6. git add . => 무대로! 

7. git commit -m '내용' => 버전 찰칵! 

8. git log --oneline => 커밋 로그 확인 
9. git remote add origin => 주소 연결 

10. git remote -v => 주소 확인 

11. git push origin master => 커밋 사항 올리기 

12. git clone 주소 => 그공간에 폴더 복제 

13. git pull origin master => 내려받기



### **자세한 버전)** **상향식**

#### **Local** 

홈폴더 - bash - mkdir acomputer - code로 열기 - pwd로 경로 확인 - touch a.txt(파일 만들기) - a.txt 클릭 후 "집에서 확인함"을 적고 ctrl+s 저장 - git init(acomputer 안에 있는 지 꼭 확인) - ls -a(숨김보기, 그럼 git 이 보임) - git status(현황 파악, a.txt :untracked files) - git add . - git status( a.txt : new files 무대에 올림) - git commit -m "내용"(버전 관리) - git status 커밋버전 관리 잘되고 있음을 확인 - git log --oneline(커밋 로그 확인) - a.txt 두번째 줄에 "로컬에서 작업함"을 작성 후 M(수정이 뜸), 저장 - git add . ※ 만약에 수정을 내리고 싶으면 git restore --staged a.txt(무대에서 내림) ※ - git commit -m "second commit" - git log --oneline ※ 만약 git diff 해쉬값 하면 다 삭제 됨

#### **github** 

래퍼지토리 생성"relay-test" - vscode로 가서 git remote add origin  주소(브릿지 연결) - git remote -v(주소 확인) - git push origin master(커밋사항 올리기)



### **자세한 버전)** **하향식**

#### **github에서 내려 받기** 

:git clone 주소(그 공간에 폴더를 복제) - git pull origin master(내려받기)

홈폴더 bash - code 깃허브 복사 - git clone 주소 - relay-test 이름을 bcomputer로 이름 변경 후 code로 열기 - ls -a(저장소), git remote -v(주소) - a.txt에 3번째 줄 "강의장에서 다운받음" 작성 후 저장 - git status (수정사항 발생) - git add . - git commit -m "mulcam" - git log --oneline - git push origin master - 그럼 a.txt에 업데이트 됨 - 원래 acomputer에 git log --oneline - git pull origin master



#### **깃허브와 vscode) 충돌과 해결방안**

홈폴더 bash에서 mkdir collision 폴더 생성 - code로 열기 - pwd 경로 확인 - touch a.txt - 1 적고 저장 - git inti - git add . - git commit -m "first commt" - git log --oneline - 깃버흐 collision-test 래퍼지토리 만들기 - git remote add orgin 주소 - git remote -v - git push origin master



##### **에러 상황)** 

깃허브 오른쪽 유혹의 연필 클릭 후 2번째 줄 "허브에서 작성함" 작성 후 commit changes - vscode에서 두번째 줄 "로컬에서 작성함" 작성 후 저장 - git add . - git commit -m"local" - git log --oneline - git push orgin master하면 에러 줄줄



##### **해결 방안)** 

git pull origin master - 한글 빼고 다 삭제 후 저장 즉 1, 로컬에서 작성, 허브에서 작성함만 남기기 - git add . - git commit -m "solve" - git push origin master



## **Branch 명령어**

\1. git branch -> 확인용 

   git branch {{ 이름 }} => 생성용 

\2. git switch 브랜치명

\3. git merge water  -> 위치는 마스터에서

\4. git branch -d water -> 쓸모없어진것 삭제



### **자세한 버전)** 

#### **Local** 

mkdir branch-test - cd branch-test - code . - git init - git branch(확인용) - touch a.txt - a.txt에

물이랑 관련없는 놀이기구

1. 티엑스프레스

작성 후 저장 - giit add . - git commit -m"first commit" - git branch

2. 자이로드롭

3. 바이킹

4. 롤러코스터

5. 회전목마

6. 디스코팡팡

작성 후 저장 - giit add . - git commit -m"second commit" - git branch - git --oneline - git branch water(생성용) - git branch( *master water 요렇게 뜸) - git switch 브랜치명(water) - 물이랑 관련있는 놀이기구

1. 후룸라이드

2. 아마존 익스프레스

3. 워터 슬라이드

작성 후 저장 - giit add . - git commit -m"water attration added" - git switch master - git switch water - git switch master - git merge water(위치는 마스터에서 water 합치기) - git log --oneline --graph

※ 브랜치 water삭제 : git branch -d water 어차피 merge해서 괜춘! ※

****

#### **Branch) 충돌과 해결방안**

branch-collision 파일 생성 후 code. - touch a.txt - git init - a.txt "처음 공총으로 작성한 내용"- giit add . - ※git commit -m"fist"(메시지를 잘 못 적은 상황) - git commit --amend - i 누르기 - 노란색부분에 first commit 작성 - esc키 누르기 - :wq - git log --oneline (바뀐 걸 볼 수 있다)※ - git  branch - git branch test - git switch test - a.txt "test에서 작성한 내용" 저장 - add - commit -m"test1" - switch master - master에서 2번째 줄 "마스터에서 작성한 내용" 저장 - add - commit -m"master1" - git merge test - **에러! 충돌!**

****

##### **해결 방안)** 

한글 빼고 다 지우고 저장 - add - commit -m"solve" - switch test - git log --oneline - switch master - git log --oneline - - git log --oneline -graph

## **Pull / Request**

### **자세한 버전)** 

깃허브 래퍼지토리 파기 - git colne 주소 - 코드로 열기 - git remote -v -touch a.txt - a.txt " 프로젝트 시작" 저장 - git add . - git commit -m"first commit" - git push origin master - git log --oneline - git branch test - git branch - git switch test - a.txt "A씨가 수정함" - git add . - git commit -m"a-branch-1" - git push origin test - 깃허브에서 확인 - compare&pull request 누르기 - create pull request 누르기 - confirm merge 누르기 - delete~ 누르기 - git switch master - git pull origin master - git branch(*master test: 이렇게 있으면 버전 관리가 되는 것이다)

## **Fork**

### **자세한 버전)** 

깃허브 주소/kakao(유저이름)

fork

bash : giit clone 코드 주소 - cd khaiii - code . 

 

## **Reset**

### **자세한 버전)** 

폴더 reset-test - code . - touch a.txt - git init - a.txt 

" 1. 영화관 도착

2. 엘리베이터 탐
3. 13층에 감

4. 자리에 앉는다

5. 스포를 들었다 "

작성 후 저장 - giit add . - git commit -m"first commit" X5(적절한 이름 넣어주기) - 복붙 파일 3개 - reset-hard/reset-soft/reset-mixed 파일명 변경

**reset-hard** 파일 코드로 열기 - git log --oneline - git reset --hard 해쉬값

**: 과거까지 시간, 작업물 싹 다 날라감**

**reset-soft/reset-mixed** git reset --soft해쉬값/ git reset --mixed 해쉬값

**: 커밋까지 날라감, 무대 위에 올라가 있음**