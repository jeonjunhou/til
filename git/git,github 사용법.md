# Git

- 분산 버전관리 시스템
  - 코드의 히스토리(버전)을 관리하는 도구
  - 개발되어온 과정 파악 가능
  - 이전버전과의 변경 사항 비교 및 분석



# GitHub

- git 기반의 원격(remote) 저장소 서비스



# Unix/Linux 명령어

1. 현재 위치의 폴더,파일 목록 보기 : ls
2. 현재 위치 이동하기 : cd <이동 할 경로>
   * 절대경로로 이동하기 : cd "C:\Users\rerea\OneDrive\바탕 화면\til\git" 문자열의 형태로 붙여 넣으면 바로 이동 가능
   * 상대경로로 이동하기 : cd ../.. 이런식으로 하면 전전 디렉토리로 이동
3. 상위 폴더로 이동 : cd ..
4.  현재 위치 : cd .
5.  ~ :  사용자 폴더를 나타내는 별명같은 문자
6. 폴더 생성하기 : mkdir <폴더이름>
7. 파일 생성하기 : touch <생성파일이름>
8. 파일 삭제하기 : rm <파일이름>
9. 폴더 삭제하기 : rm -r <폴더이름>
10. 경로 나온거 닫기 : clear



# Git 기본기

- Repository : 특정 디렉토리를 버전 관리하는 저장소
  - git init 명령어로 로컬 저장소를 생성
  - .git 디렉토리에 버전관리에 필요한 모든 것이 들어있다

- 커밋(commit) : 특정 버전으로 남긴다
  - 커밋은 3가지 영역으로 동작한다
    1. Working Dircectory : 내가 작업하고 있는 실제 디렉토리
    2. Staging Area : 커밋으로 남기고싶은, 특정 버전으로 관리하고싶은 파일이 있는 곳
    3. Repository ; 커밋들이 저장되는 곳

- 명령어
  - git init : 로컬 저장소를 생성 (.git)
  
  - git status : 현재 파일의 상태를 나타내 준다
  
  - git add : 파일이 버전관리를 시작하도록 변환해주는 것
  
  - git add. : 추적되지 않은 모든 파일과 수정된 파일을 모두 Staging Area로 올려준다
  
  - git commit : 파일을 버전으로 된 형태로 변환 해준다
  
  - git commit -m "(commit_message)" : 커밋에 대한 메세지를 설정
  
  - git log : git의 커밋 히스토리 보기
  
    - git log --graph : branch 히스토리를 볼수 있음
    - git log --graph --oneline : branch 히스토리를 간략하게 볼수 있음
  
  - git diff : 두개의 커밋간에 차이 보기
  
  - git restore --staged {file name} : git add. 한상태에서 Working Dircectory 되돌릴때 사용
  
  - git restore : 가장 최신커밋과 비교해서 Working Dircectory 있는 내용을 되돌린다
  
    > 작성했던 부분이 전부 날아갈 수 있으니 주의해야 한다 !!!
  
  - git reset --hard {c_id} : 커밋을 되돌린다 (경험만 해보자)

|       | WD   | SA   | RP   |
| :---- | ---- | ---- | ---- |
| soft  | X    | X    | O    |
| mixde | X    | O    | O    |
| hard  | O    | O    | O    |

- O : 과거의 커밋의 모습으로 돌아갑니다.

- X : 현재 내가 작업하고 있는 모습이 그대로 남아있습니다.

  - gitignore :  .gitignore

    > .git 과 같은 공간에 .gitignore를 만들고 그안에 아래 형식으로 넣어주면 제외시킬 수 있다

       - data.csv #특정 파일
       - secret/ #특정 폴더
       - *.png #특정 확장자
       - !profile.png #모든 png 파일은 빼고 profile.png는 넣고
       - gitignore.io 사이트에서 기본적으로 키워드를 입력하면 그에 맞는 ignore 파일이나 확장자를 알려줌

  - 

- git / github연결
  - git config --global user.email " "
  - git config --global user.name " " 

- 

### remote 명령어

__windows에서는 git bash 에서 사용__

- git remote add origin {주소.git} : 로컬과 깃허브 연결
- git push -u origin master : 깃허브에 로컬에 있는 부분을 push
  - -u : set-upstream 처음 push 할때 사용해주면 그다음에 push할때에는 git push만 써도 되도록 하는 명령어 라고 보면 된다 (로컬 저장소에서 원격저장소로 연결 했을 때사용/ 원격저장소에서 로컬저장소를 연결 했을 때에는 자동적으로 셋팅이 된다)
- git pull origin main : 리모트에 있는 최신 버전의 내용을 로컬로 당겨오는 것
- git clone {remote_repo} : remote에있는 repository 를 로컬로 복사



# Branch

특정 커밋을 가르키는 포인터

### Branch basic commands

1. branch 생성 : (master)$ git branch {branch name}
2. branch 이동 : (master)$ git checkout {branch name}
3. branch 생성 및 이동 : (master)$ git checkout -b {branch name}
4. branch 목록 : (master)$ git branch
5. branch 삭제 : (master)$ git branch -d {branch name}
6. branch 합체 : git merge {결합할 branch name} 결합해서 흡수할 branch 에서 실행 
   - ex) A branch 에다가 B branch를 결합 하고 싶으면 A branch 위에서 git merge B 를 하면 된다
7. git log --graph : branch 히스토리를 볼수 있음
8. git log --graph --oneline : branch 히스토리를 간략하게 볼수 있음

> > 위 7,8 은 git 기능이긴 하지만 branch 관련 기능이기에 한번더 명시함

9. 기존 branch에 변경이 없으면 단순히 앞으로 이동 : git merge {branch name} -fast -forward



#### Git Flow 에 대해서 알아보자.











