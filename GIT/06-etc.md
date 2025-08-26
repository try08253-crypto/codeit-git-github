# 기타

## clone
- git clone [리모트리포지토리주소]
- 위 명령어는 다음 명령어를 차례대로 실행한 결과와 같다.
  - 상황: 내가 처음 팀에 합류한 상황
  - 작업
    - 프로젝트 폴더를 생성한다
    - git init
    - git remote add origin [리모트리포지토리주소]
    - git fetch: 리모트 리포지토리에 있는 모든 브랜치의 트래킹 브랜치를 생성합니다.
      - 현재 시점의 브랜치 상태: origin/main, origin/develop
    - git checkout -t origin/develop
      - origin/develop과 동일한 범위를 가지는 develop 브랜치를 생성하고 체크아웃
    - 작업을 진행한다.

## pull
- git pull origin develop --rebase
  - git fetch origin develop
  - git rebase origin/develop: 충돌이 날 수 있다

- git pull origin develop --no-rebase
  - git fetch origin develop
  - git merge origin/develop
    - 3 way merge가 되거나: 충돌이 날 수 있다
    - fast forward 머지가 되거나: 충돌이 날 수 없다

- git pull origin develop --ff-only
  - git fetch origin develop
  - git merge origin/develop: 반드시 fast forward 머지만 진행한다.

- git pull origin develop 명령어를 입력하면
  - 만약, 옵션을 쓰는 경우에도 동일한 커밋 히스토리가 만들어 지는 경우 문제없이 진행된다.
  - 만약, 옵션을 쓰는 경우에 따라서 다른 커밋 히스토리가 만들어 지는 경우 어떤 옵션을 사용하고 싶은지 개발자에게 질문한다.
    - 그런데, 이 질문마저도 내가 받고 싶지 않다면
    - 내가 무엇을 선택할지 미리 등록해두면 됩니다.
      - git config pull.rebase true: 선택의 순간이 오면 무조건 rebase
      - git config pull.rebase false: 선택의 순간이 오면 무조건 merge
      - git config pull.ff only: 선택의 순간이 오면 무조건 fast forward only