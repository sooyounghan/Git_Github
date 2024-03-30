-----
### Log 명령어
-----
1. 각 Commit마다 변경사항 함께 보기
```
git log -p
```

2. 최근 n개 커밋만 보기
```
git log -(개수)
```
  - 최근 n개의 커밋을 보는데, 각 commit마다 변경사항 함께 보기 : git log -p -(개수)

3. 통계와 함께 보기
```
git log --stat
```
  - 더 간략히 보기 : --shortstat

4. 한 줄로 보기
```
git log --oneline
```
  - --pretty=oneline --abbrev-commit의 줄임물

5. 변경사항 내 단어 검색
```
git log -S (검색어)
````
  - George로 검색 : git log -S George
  - George와 관련된 Commit 추출

6. 커밋 메세지 중심
```
git log --grep (검색어)
```
  - Commit 메세지에 검색어가 포함된 Commit 추출
  - 기타 제한 옵션 : https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0#limit_options

7. 자주 사용되는 그래프 로그 보기
```
git log --all --decorate --oneline --graph
```
  - --all : 모든 branch 보기
  - --graph : 그래프 표현
  - --decorate : branch, tag 등 모든 reference 표시
    + --decorate=no
    + --decorate=short : 기본
    + --decorate=full
   
  - Source Tree 사용하는 것이 더 바람직!

-----
### 포맷된 Log 보기
-----
1. 관련 주소 : https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0#pretty_format
2. 예시
```
git log --graph --all --pretty=format:'%C(yellow) %h  %C(reset)%C(blue)%ad%C(reset) : %C(white)%s %C(bold green)-- %an%C(reset) %C(bold red)%d%C(reset)' --date=short
```
  - date=relative : 오늘 기준 몇일/몇달 전으로 상대적 기준으로 변경
  - 단축키로 등록하여 사용
```
git config --global alias.(단축키) "git log --graph --all --pretty=format:'%C(yellow) %h  %C(reset)%C(blue)%ad%C(reset) : %C(white)%s %C(bold green)-- %an%C(reset) %C(bold red)%d%C(reset)' --date=short"
```



