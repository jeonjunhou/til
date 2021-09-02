# Git

- 분산 버전관리 시스템
  - 코드의 히스토리(버전)을 관리하는 도구
  - 개발되어온 과정 파악 가능
  - 이전버전과의 변경 사항 비교 및 분석



# GitHub

- git 기반의 저장소 서비스



# Unix/Linux 명령어

1. 현재 위치의 폴더,파일 목록 보기 : ls
2. 현재 위치 이동하기 : cd <이동 할 경로>
3. 상위 폴더로 이동 : cd..
4. 폴더 생성하기 : mkdir <폴더이름>
5. 파일 생성하기 : touch <생성파일이름>
6. 파일 삭제하기 : rm <파일이름>
7. 폴더 삭제하기 : rm -r <폴더이름>
8. 경로 나온거 닫기 : clear



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
  - git diff : 두개의 커밋간에 차이 보기



- git / github연결
  - git config --global user.email " "
  - git config --global user.name " " 

- git remote add origin {주소} 로컬과 깃허브 연결
- git push -u origin master 깃허브에 로컬에 있는 부분을 push
- git clone {remote_repo} : remote repo 를 로컬로 복사



