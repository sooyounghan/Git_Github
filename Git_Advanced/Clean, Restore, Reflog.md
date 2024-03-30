-----
### 관리 되지 않는 파일 삭제하기
-----
```
git clean -옵션
```
1. Git에서 추적하지 않는 파일 삭제
2. 옵션
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e363e66b-8b38-48b3-9552-13d26cc1fc58">
</div>

  - 위의 옵션들을 조합해 사용

3. 파일들을 추가한 뒤 옵션 조합과 함께 clean 명령어 사용 예제
   - toClean1.txt
   - toClean2.txt
   - dir/toClean3.txt
  
   - git clean -n을 통해 확인하면, 현재 폴더에서의 폴더내에 생성한 파일 외 2개 파일만 보여줌
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ae7e4292-b8a7-4552-bd33-a4ad2a10a23c">
</div>

   - 디렉토리까지 포함해서 보고 싶다면, git clean -nd
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/afa5f7c3-baf3-4f80-acea-215372a31f74">
</div>

   - git clean -di를 하면, 전체 관리되지 않는 내용에 대해 interactive 실행
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a5a71e08-e378-4fdf-a8b0-66a2958f50f7">
</div>

   - git clean -f : 모두 강제 삭제 (-df : 폴더 포함)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/94ffc7fc-2e30-4f4a-9197-ec986b22ea2f">
</div>

-----
### 커밋하지 않은 변경사항 되돌리기
-----
```
git restore (파일명)
```
1. 특정 파일을 지정된 상태로 복구 (예전 명령어 : git chekcout)

2. 예제 : 파일 여러 개를 수정하고 아래 명령어 사용 ( working directory 존재 )
   - panthers.yaml의 내용을 기존으로 복구하고 싶으면, 다음과 같이 하면 복구
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/27a9e953-57fb-40d9-a177-89ebbbc8fe1d">
</div>

   - 전체를 복구하고 싶으면, git restore .
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/00a3338c-0ec7-4864-86f9-0851d7013043">
</div>

3. 이번에는 2번 상황에서 staging 영역에 존재한다고 하면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6da91013-5c41-49dc-837c-631b5aac2baa">
</div>

```
git restore --staged (파일명)
```
   - panthers.yaml의 내용을 기존으로 복구하고 싶으면, 다음과 같이 하면 복구
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cf4ef1ce-cf5d-44df-978a-7901d826037e">
</div>

   - 전체를 복구하고 싶으면, git restore --staged .
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a6440c05-8cf7-4295-ac4a-67e553236b7a">
</div>

-----
### 파일을 특정 커밋 상태로 되돌리기
-----
```
git restore --source=(HEAD 또는 Commit Hash) 파일명
```

1. Commit이 변한 것이 아니라, 파일의 상태만 특정 상태로 되돌리는 것
2. Commit이 'Add George to Tigers'로 되돌리고 싶다면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/efdfd9a9-483d-4dd2-9fed-4d9e2208bed2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/84d7da69-5160-4b69-bcd3-654b3b6b0bff">
</div>

  - 파일의 상태만 되돌린 것이기에, Commit 입장에서는 파일의 변경된 것으로 간주되어 다음과 같은 결과

-----
### Reflog
-----
1. reset으로 사라진 Commit을 복구할 수 있는 명령어
2. 예를 들어, 현재 다음과 같이 프로젝트가 진행중이었다고 하자.
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2b31a227-1510-4171-8fae-0426d038e170">
</div>

   - 여기서 다음과 같이 reset을 하게 되면 ? (git reset --hard HEAD~15)
   - 최근 15개의 Commit이 삭제되었고, 더불어 git log에도 보이지 않음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9f18ce98-d806-406b-ba3f-2330ec6f39e1">
</div>

   - 해결 방법
```
git reflog
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/54ebe208-a01e-4552-9878-d93257b49654">
</div>

  - reflog는 프로젝트가 위치한 Commit이 바뀔 때마다 기록되는 내역을 보여줌
  - 이를 통해 reset 하기 이전 시점으로 프로젝트 복구 가능
  - 예를 들어, 해시값이 a89c095인 commit 시점으로 복구하고 싶다면, git reset --hard a89c095로 복구 가능
  - 또한 위의 단계에서 reset 후, 다시 git reflog를 적용하면 위 적용단계까지 모두 그 log가 반영

  - 즉, 내가 수행한 Git 작업을 기준으로 과거 내역을 살펴보고 프로젝트를 되돌릴 수 있음
