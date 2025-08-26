# 깃

## 버전 관리 시스템(깃)
- 프로젝트 폴더를 버전별로 저장할 수 있는 시스템

## 깃 설치
- 윈도우: 설치 프로그램 다운 받아서 설치
- 맥: Homebrew를 이용해서 설치

## 깃 사용자 설정
- git config --global user.name "깃허브사용자이름"
- git config --global user.email "깃허브계정이메일"
- git config --global init.defaultBranch main

## 깃 사용 방법
1. 프로젝트 디렉토리를 깃으로 관리하기 시작한다.
- git init
- .git 폴더가 생성된다(숨김 폴더)

2. 깃으로 관리하는 프로젝트 디렉토리는 아래의 3단계로 구분된다.
- 워킹 디렉토리(디렉토리)
  - Tracked: 스테이징 에어리어에 기록된 파일 및 폴더
  - Untracked: Tracked를 제외한 나머지 전부
- 스테이징 에어리어(장바구니)
- 로컬 리포지토리(구매내역)

3. 현재 프로젝트 폴더의 상태를 파악해보자
- git status
  - 로컬 리포지토리와 스테이징 에어리어의 차이를 보여줍니다.
  - 스테이징 에어리어와 워킹 디렉토리의 Tracked의 차이를 보여줍니다.
  - UnTracked를 보여줍니다.

4. 현재 프로젝트 폴더 상태를 저장해보자.
- git commit -m "메세지"
- 메시지를 잘 쓰는 방법: 팀에서 논의해서 결정한다.

5. 저장된 기록을 확인해보자.
- git log

6. 다른 저장 기록으로 이동하기
- checkout: HEAD를 이동시킨다.
- git checkout [브랜치이름]
  - HEAD가 브랜치를 가리킨다.
- git checkout [커밋아이디]
  - HEAD가 특정 커밋을 가리킨다.
  - HEAD가 브랜치에서 이탈(detached)했다.

7. 브랜치를 만들어보자
- git branch
- git branch -r: 트래킹 브랜치의 목록을 보여준다
- git branch [브랜치이름]
- git checkout [브랜치이름]
- git branch -D [브랜치이름]: 브랜치를 삭제한다
- 브랜치의 범위
  - 브랜치 화살표가 가르키는 마지막 커밋으로부터
  - 찾을 수 있는 모든 부모 커밋을 전부 포함한다.