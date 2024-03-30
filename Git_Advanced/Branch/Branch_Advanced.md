-----
### Fastforward vs 3-way merge (Merge 전략)
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/97cf19b5-6c28-45db-9f7d-25123231f9f3">
</div>

1. Fastforward : rebase
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6207a139-9d5d-40ee-ba0f-af354a3af129">
</div>

  - 두 branch(A[Main], B)가 공통 Commit을 조상으로 가지고 있음
  - 한 쪽 branch(B)에 이후의 Commit이 있을 때, 굳이 다른 Commit을 만들지 않고 A의 branch HEAD를 B의 branch HEAD로 옮기는 방법
  - A의 branch에서는 변화가 없으므로 B의 branch와 병합해도 문제 발생 없음
  - 이후, 병합된 Branch는 삭제

  - 단점 : 이 작업을 한 후, 어떤 Branch 사용 및 언제 병합했는지 기록이 남지 않게됨
    
2. 3-way merge : merge
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d0f68203-e372-4164-94a7-75d4788d2ce4">
</div>

   - 원래 Branch의 변화가 없어도 기록 변화와 어떤 Branch 사용을 했는지 History를 남기기 위해 병합 Commit을 만들어 Merge
   - 양쪽 branch 모두 Commit이 하나 이상 있다면, 병합 Commit을 만들어 Merge

   - 내부 원리
     + 두 Branch가 병합할 때, 두 Commit 모두에 속한 어떤 파일들이 양쪽에 내용이 다르다면?
     + Git은 그 파일들 각각이 A, B branch 각각에서 변경된 것인지, 아니면 모두 변경된 것인지 알 수 없음
     + 즉, 충돌의 원인을 파악할 수 없음
     + 이를 판별하기 위해, 이 두 branch의 공통 조상이 되는 Commit의 내용과 둘의 내용을 대조
     + 따라서, 차이가 있는 파일들마다 어떤 것을 병합에 반영해야 하는지, 어떤 것을 충돌의 원인으로 인식해서 사용자에게 해결을 맡길지 merge 과정에서 결정을 내리게 됨
     + 즉, 3-way는 A / B / A와 B의 공통 조상을 의미
       
```
git merge --no-ff (병합할 브랜치명)
```
   - --no-ff : no fastforward, 즉 fastforward를 하지 않는 다는 것을 의미

-----
### 다른 Branch에서 원하는 Commit만을 가져오기
-----
1. 현재 프로젝트의 구성도
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1e927ab0-0343-4bd2-a4b6-89b3a71530e1">
</div>

2. 다른 브랜치의 원하는 커밋 가져오기 : cheery-pick 명령어 사용
3. Cherry Commit을 main branch로 가져오기
   - main branch에서 실행
```
git cherry-pick (해당 커밋 해시)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8e545a5e-1182-4fc7-a523-250032ef3dbc">
<img src="https://github.com/sooyounghan/Web/assets/34672301/71c403c9-5c0d-407e-a6fe-ba376b61842c">
</div>

  - Fruit branch에 있던 Cherry Commit이 Main branch로 가져오게 된 것을 볼 수 있음
  - 즉, Merge와 Rebase와 달리, 단지 그 Commit을 복제해서 가져오는 개념 (두 Cherry는 다른 Commit)
  - 참고 : Source Tree는 항상 가장 최근에 실행된 Commit을 기준이 다음과 같이 보임

-----
### 다른 Branch에서 파생된 Branch를 옮겨 붙이기
-----
1. rebase --onto 옵션
```
rebase --onto (도착 브랜치) (출발 브랜치) (이동할 브랜치)
```

2. Main branch에서 특정 기능 구현을 위해 branch를 나누어 작업하다가, 보조 기능을 또 branch로 나누어 작업
   - 이후, 특정 구현을 위한 큰 branch 기능을 사용하지 않았지만, 보조 기능의 branch는 사용해야 될 때 해당 기법 사용
     
3. fruit Branch에 파생된 citrus branch를 main branch로 옮겨붙이기
```
git rebase --onto main fruit citrus
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3d5e7095-f53d-435f-9f03-5cad7fe28446">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c19a325b-16ce-4bff-8316-a7c69638d5aa">
</div>

  - 즉, fruit branch 내 citrus branch가 사라지고, 이 branch가 main branch로 이동 된 것을 볼 수 있음
  - 이제 main branch의 HEAD를 citrus와 일치시켜주면 됨
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8a87b997-f66d-4cbf-a307-49b4329091cb">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1486263a-d4da-4a3f-a64e-ac8c59b7ba16">
</div>

4. rebase --onto를 되돌리기 위한 방법
   - 위의 사항을 진행 후, git reflog를 실행하면 다음과 같음 (rebase --onto 명령 간 여러 내역이 처리됨을 볼 수 있음)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/02628347-f0c9-46bd-b7d6-bb4acd4a4280">
</div>

  - 즉, rebase --onto가 여러 동작을 포함하는 것을 알 수 있음
  - 이 과정에서, 이전 상태로 돌리기 위해서는 reset은 브랜치 별로 이루어지므로, 이 영향을 받은 모든 branch를 하나하나 reset 하거나 혹은 다시 옮겨 붙이는 방법

    + main branch : main은 옮겨붙여진 citrus로 fastforward된 것이 마지막 액션이므로 reflog 기록상에서 그 이전 기록으로 reset --hard를 하면 끝
    + citrus branch
      * 방법 A : citrus branch는 해당 branch가 옮겨지기 전 마지막 커밋인 commit:Lime 부분을 reflog에서 찾아 reset --hard
      * 방법 B : 다시 rebase --onto를 사용해 citrus의 commit을 main으로부터 다시 fruit branch의 orange 부분으로 옮기는 것
        - 이를 위해서는 orange commit으로 checkout 한 다음 새로운 브랜치를 생성 (temp)
        - git rebae --onto temp main cirtus로 cirtus의 두 commit을 해당 위치로 옴긴 뒤 temp branch 삭제
          
-----
### 다른 Branch에서 파생된 Branch를 옮겨 붙이기
-----
1. 다른 커밋들을 하나로 묶어 가져오기
```
merge --squash (대상 브랜치)
```
2. root branch의 마디들을 하나로 묶어 main branch로 가져오기
```
git merge --squash (대상 브랜치)
```
  - merge가 완료된 것이 아닌, 이 branch들이 옮겨 붙여져서 add가 되어 현재 staging되는 것임
  - 따라서, commit을 해줘야 함을 주의
  - 또한, root branch는 기존 branch를 유지하며, 그 branch만 옮겨 붙여진 것
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f045b1c8-c679-4211-9a84-769bf36d8b00">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3f95b1da-7545-421d-9ec4-4ccedb4ac5b8">
<img src="https://github.com/sooyounghan/Web/assets/34672301/be65de2f-59a9-43c9-8007-35afcb3572df">
<img src="https://github.com/sooyounghan/Web/assets/34672301/82ce1cb8-0b67-463b-838f-d270144b51db">
</div>

3. 일반 merge와의 차이점
   - 실행 후 코드의 상태는 같지만 내역 면에서 큰 차이가 발생
   - 일반 merge : A와 B 두 branch를 한 곳으로 이어 붙임
   - merge --squash : B branch의 마디들을 복사해 한 마디로 모아 A branch로 붙임 (staged 상태)
