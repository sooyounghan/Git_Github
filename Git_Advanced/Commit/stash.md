-----
### git stash
-----
1. 변경사항 만들기
   - Tigers의 members에 Stash 추가
   - tomcats.yaml 추가 후 add

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/06758309-0714-41b2-ba6b-2092600eb636">
</div>

2. 이 상태에서 git stash를 하면,
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f85e9420-4501-4991-90d2-c171a0586940">
</div>

3. 이를 확인하는 방법은 Source Tree의 스태시 부분 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/bae46f94-68c3-4558-82cf-2fe703ba7b85">
</div>

4. 다른 작업을 하다가 같은 / 다른 Branch에 같은 Commit / 또다른 Commit에 가능

5. 원하는 시점, branch에서 다시 적용
```
git stash pop
```

6. new-branch에 stash 해둔 사항 pop 후 commit도 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9b7ec032-feb7-4f69-a191-be451b14e138">
</div>

-----
### 원하는 것만 stash
-----
1. 예시
  - Leopards의 members에 Stash2 추가
  - Jaguars의 members에 Stash3 추가

2. 원하는 부분만 stash
```
git stash -p
```
  - 가장 마지막에 한 부분부터 시작
  - stash2만 stash 하고, 나머지는 하지 않음

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/92fbf74e-5016-4ff2-a494-376b75d89e56">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a89f9fa4-fa28-43ef-804c-2c56a8b68290">
</div>

  - stash3은 stash 하지 않았으므로 존재하지만, stash2는 stash했으므로 존재하지 않음

3. 메세지와 함께 stash
```
git stash -m "메세지명"
```
  - stash3을 stash 하기 위해 git stash -m 'Add stash3'
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cd0e532d-6139-4583-814e-672d30e3ff05">
</div>

-----
### stash 목록 보기
-----
```
git stash list
```
  - 리스트상 번호로 apply(list에서 불러오기), drop(list에서 지우기), pop(불러오면서 list에서 지우기) 적용 가능
  - 적용한다는 것은 단지 stash된 것을 파일로 불러오는 것 (add, commit 되는 개념이 아님)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e52f2634-2220-4deb-9a72-5020f8f84b03">
</div>

  - stash{1} 부분을 stash 한 후, stash list에서 지우고 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9db3e29b-63c3-4f98-aea7-21ccfdef77f4">
<img src="https://github.com/sooyounghan/Web/assets/34672301/95c9a557-89f0-4f54-8d39-77bd9b15a809">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4b2329c1-f147-46ec-b73d-6cc67b394902">
</div>

  - stash{0} 부분을 stash pop한 후, stash list 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1166cf07-acfd-4538-b10d-c60f5ece6e96">
</div>

-----
### stash 명령어
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5b991a74-5e54-4f9f-9ca9-cbf0d8b58c58">
</div>

+ git stash branch 예제
  - stash4 데이터를 추가한 후, stash로 처리한 후 새로운 stash-branch 생성 후 해당 stash를 pop
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9f08eb1e-c791-42c2-9477-61d00a223286">
</div> 

  - 충돌 문제를 방지하기 위해 먼저 stash를 새로운 branch에 처리한 후 main branch는 충돌 문제 해결 후 merge
  - 충돌 사항이 있는 상황 등 유용

-----
### Source Tree 실습
-----
1. 상단 메뉴에 스태시로 stash 지정 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0a5c00ae-5b41-49af-87e2-f9d5b6809931">
</div> 

2. stash 지정 시 메세지 지정 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1a109d0c-fee2-43cb-820b-8ce2013be035">
</div> 

3. 스태시로 stash 내역 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cf521a52-7409-4847-967b-6e846573012b">
</div> 

4. stash에 대해 apply, drop, pop 설정 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/22a03f0a-a7af-4e3f-95aa-7c44a2b7e954">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d7441543-41d0-44c8-aae7-de80aa808909">
</div> 

