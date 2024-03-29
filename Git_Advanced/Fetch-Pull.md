-----
### Fetch 와 Pull 차이
-----
1. Fetch : 원격 저장소의 최신 Commit을 로컬 저장소로 '가져오기만' 함
   - 원격 저장소에 특정 Commit을 추가되었고, 아직 로컬 저장소에서 그에 대한 것이 없을 때, Fetch를 하면?
   - 현재 로컬 저장소의 Main HEAD는 유지하되, 가상의 Branch를 하나 받아와서 원격 저장소의 정보를 받아옴
   - 하지만, Pull 처럼 merge나 rebase하지는 않음
2. Pull : 원격 저장소의 최신 Commit을 가져와 merge 또는 rebase (즉, Fetch의 과정을 포함)

-----
### Fetch한 내역을 적용하기 전 살펴보는 방법
-----
1. 원격의 Main branch에 Commit 추가
   - 원격의 Main branch에서 tigers.yaml에 Fetch : this 추가 후 Commit
   - git checkout origin/main 이용
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d05d8beb-bd9a-4a39-89ae-dfdc6c4e2558">
<img src="https://github.com/sooyounghan/Web/assets/34672301/14438613-7928-45dd-ae5c-e92e8c77ce9f">
<img src="https://github.com/sooyounghan/Web/assets/34672301/be85915b-ad2e-47f8-ade3-d55a7ad2ead1">
</div>

2. 현재 origin/main이라는 익명 branch에 존재하고 있지만, Fetch를 하지 않았으므로 아직 Fetch : this는 보이지 않음

3. 다시 로컬의 main branch로 이동 후, git fetch를 하게 되면 현재 원격의 Fetch : this가 로컬에도 최신화
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/21dd08b5-8d77-4fdc-9c4a-881cb7eb5c83">
</div>

4. 다시 한 번 git checkout origin/main을 하게 되면, 해당 내용이 보임
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/177ebee9-c87c-4205-98b1-b5adf0f33857">
</div>

5. 확인 후, 다시 main branch로 이동 후, git pull하면 정상적으로 로컬에도 적용
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/93ba6677-2e82-4224-9946-832afd9d8a21">
</div>

-----
### 원격의 새로운 Branch 확인
-----
1. 원격에서 new-branch라는 새로운 branch 생성 후, 해당 branch에서 tigers.yaml의 내용 추가
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/7efc7b46-82f2-4f3f-9167-fb5e3662c3db">
</div>

2. 로컬에서 git fetch를 하면 새로운 branch가 나온 것을 볼 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/60b30a9e-1c74-46f8-b806-98fe9f2b224d">
</div>

3. git branch -a을 하면, 새로 추가된 원격 branch를 확인할 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a997d0f8-00f7-4ab5-a608-dd5988d06685">
</div>

4. 해당 branch를 pull해서 받지 않고, 원격 branch에 접근해서 해당 commit된 부분을 보고 싶다면?
   - git checkout origin/new-branch로 접근해서 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3be9da3f-c61f-44d8-840f-5a47fc106624">
</div>

   - 원격의 origin/new-branch를 로컬에도 받아오고 싶으면, git switch -t origin/new-branch 입력
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e8ca6e5a-c3e3-41ac-87fb-d822dab653c1">
</div>



