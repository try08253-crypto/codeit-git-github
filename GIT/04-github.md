# Github

## 정의
- 깃으로 관리되는 프로젝트를 저장하고 공유할 수 있는 클라우드 서비스

## 인증
- 유저아이디, 토큰
- 토큰을 로컬에 저장하고 사용합니다.
  - 인증 초기화
    - git config --global --unset credential.helper
  - 인증 등록
    - 보안에 취약한 방법
      - git config --global credential.helper store
      - 토큰이 암호화되 않고 평문으로 저장됩니다.
        - Mac: ~/.git-credentials 파일에 저장됩니다.
        - Window: C:/Users/[계정이름]/.git-credentials 파일에 저장됩니다.
    - 보안에 좋지만 귀찮은 방법
      - git config --global credential.helper cache --timeout=3600
      - 토큰이 메모리에 저장됩니다.
    - 보안에 좋은 방법
      - 토큰이 암호화되서 저장됩니다.
        - Mac: git config --global credential.helper osxkeychain
        - Window: 자동으로 된다...(Git을 설치할 때 Git Credentail Manager가 자동으로 설치되어서 암호화를 해결한다)









## 로컬과 원격의 연결
- git remote add [원격리포지토리주소의별명] [원격리포지토리주소]
- git remote add origin [원격리포지토리주소]
- git remote -v: 등록된 원격리포지토리주소의별명과 주소를 보여준다.

## 업로드
- git push [원격리포별명] [업로드하고싶은브랜치이름]
  - git push origin chat
  - 리모트 리포지토리에 chat 브랜치가 업데이트가 됩니다.
  - 로컬 리포지토리에 트래킹 브랜치 origin/chat이 리모트 브랜치와 동기화 됩니다.

## 다운로드
- git fetch [원격리포별명] [다운로드하고싶은브랜치이름]
  - git fetch origin dev
  - 로컬 리포지토리에 origin/dev 이름을 가진 트래킹 브랜치가 생성됩니다.
  - 트래킹 브랜치는 그림자 브랜치입니다.(체크아웃 X, 커밋 X)