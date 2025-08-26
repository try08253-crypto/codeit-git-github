# Cancel 시리즈

## reset(이미 완료된 커밋들을 최신부터 순차적으로 취소할 때)
- 커맨드
  - git reset --soft HEAD~1
    - 브랜치의 범위만 축소
    - 커밋하기 직전으로 회귀
  - git reset --mixed HEAD~1
    - 브랜치의 범위 축소, 스테이징 에어리어 리셋
    - 커밋하고 add 하기 직전으로 회귀
  - git reset --hard HEAD~1
    - 브랜치 범위 축소, 스테이징 에어리어 리셋, 워킹 디렉토리 Tracked 리셋
    - 커밋하고 add 하고 작업하기 직전으로 회귀
- 기타 사항
  - git reset --hard HEAD~1 = git reset --hard HEAD^
  - git reset --hard HEAD~2 = git reset --hard HEAD^^
  - git reset --hard [커밋아이디]

## revert(이미 완료된 중간에 어떤 커밋을 취소할 때)
- 커맨드
  - git revert HEAD
  - git revert [커밋아이디]
    - 해당 커밋의 역변환이 되는 새로운 커밋을 생성합니다.
  - 충돌
    - 직접 "수동으로" 충돌을 해결한다.
    - 직접 "수동으로" 스테이징 에어리어에 add 한다.
    - git revert --continue

## stash(스테이징 에어리어에서 진행된 작업을 잠시 취소할 때)
- git stash: 현재 스테이징 에어리어에 상태를 잠시 옆에 치워놓는다.
- git stash drop: 옆에 잠시 치워둔 상태를 제거해버린다.
- git stash pop: 옆에 잠시 치워둔 상태를 다시 스테이징 에어리어에 덮어쓴다.
