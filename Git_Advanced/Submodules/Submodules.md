-----
### 서브모듈 (Submodule)
-----
1. 프로젝트 폴더 안에 또 다른 프로젝트가 포함될 때 사용
2. 여러 프로젝트에 사용되는 공통 모듈일 때 유용
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/41d243ff-3755-443a-b496-e1ca200ce384">
</div>

   - 즉 현재 main-project의 git은 main-project-files만 관리
   - module-project-1과 module-project-2는 각각의 해당하는 git이 있으므로 main-project의 git이 관리하지 않도록 설정하는 방법
   - 대신 메인 프로젝트와 서브 프로젝트의 관계는 git 정보로 가지고 있는 것
  
3. Main Project 폴더 생성 후 main.txt 내용 추가 후 Commit
   - Remote Reposiotry에 Push하기 위해 main-project 생성 후 push
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d688f06b-3037-45f4-be30-3f5f1041f20e">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/454737e3-8749-43e8-b826-28d80a0311bd">
</div>

4. Submodule도 동일하게 생성 (팀원들 간에 공유되는 Module용 Project)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/cf19ffba-bd0d-49f7-966d-e66a85dcdbf0">
</div>

5. Main Project에 서브모듈로 submodule 프로젝트 추가
  - main-project 디렉토리 상 터미널에서 아래 명령어 실행
```
git submodule add (submodule의 GitHub 레포지토리 주소) (하위폴더명, 없을 시 생략)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/25f1405c-4b70-4a34-9bf5-3d3bf7412a24">
</div>

  - submodule 디렉토리가 생기고, sub 파일과 .gitmodules 파일 생성 (submodule의 이름과 해당 url 주소 포함)
  - git status를 하면, 아직 이 파일들이 staging area에 위치함을 알 수 있으므로, Commit 실행
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c8cb4506-b0a4-48c0-9fe0-03bfe2529efd">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/0a24ba28-f250-4b5b-a348-6ffc5f15b178">
</div>

6. main.txt 및 sub 파일 모두 변화 후 git status
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/266ded30-9a2a-4739-9dd7-b71d1b44c376">
</div>

  - 두 파일 모두 변경사항 감지
  - git add .를 하면, main.txt는 staging area에 존재하지만, sub는 아직 working directory에 존재
  - 즉, Main Project의 git은 Main project 안에 위치 했으므로, Submodule에게 직접적 관여가 되지 않음을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/15d63058-3208-49bd-9cd6-0f2cad328ead">
</div>

  - Commit 후, Push 해주면 Main Project에만 적용
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/fcec644a-affb-45ae-8885-ec5596ec3cac">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/cbed03c6-ccbe-4a32-9f35-be650c228eaf">
</div>

6. Submodule 업데이트
  - submodule로 이동하려면, 터미널 창이나 새로운 프로젝트를 열고, submoudle이 있는 위치로 이동
```
cd submodule/
```
  - 해당 지점으로 이동하게 되면, 이제는 submodule의 git에 의해 동작
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/5720b274-5f06-4d8e-86e7-12c7de3d5b49">
</div>

  - 따라서, sub 파일을 add한 뒤, commit하면 자연스럽게 submodule의 git에 동작하며, 연속적으로 push도 가능 (명령어 2개 이상 : 세미콜론 표시)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/786406aa-dc49-40a5-b261-fd0ecdbd5b1c">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/56087a1c-6fc4-4b00-803a-c0ebf8744f82">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/db7df3dc-593f-4286-a494-d9f024fc5537">
</div>

 - 현재 submodule은 Commit 발생
 - 이 상태에서 Main Project로 git으로 이동해 git status를 하면, new commit이 되었다는 것을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/ba4e016c-7227-48fe-8bd2-29f3823cfeab">
</div>

 - git add 후, 다시 확인하면, 위의 내용을 commit할 준비 완료
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/2e0150ba-354c-4a46-9df9-9f16178d9aed">
</div>

 - 즉, submodule을 포함한 프로젝트는 파일의 변경사항에는 관여하지 않지만, Commit의 발생은 관여
  
 - commit후, push하게 되면, Main Project의 상태는?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/b53c561b-4b04-4c9e-997e-f475c9e21c30">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/6f25a71b-69de-4552-9520-08f50cd1e2ac">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/6dc74e2a-9522-4914-9b07-d21a0278dd35">
</div>

 - 다음과 같이 나타나며, submodule의 폴더를 클릭하면, submodule Repository로 이동

-----
### 서브모듈 (Submodule) 업데이트
-----
1. 만약, 위의 Main Project를 다른 곳에서 Clone 후 사용한다면 ? Submodule의 폴더는 생성되나 내부 파일들은 되지 않음
2. 따라서, Submodule Init 후 Clone 필요
```
git submodule init (특정 서브모듈 지정 시 해당 이름)
git submodule update
```
  - 특정 서브모듈 지정 시 해당 이름 : .gitsubmodules 내의 [submodule="..."]의 안의 submodule 기준으로 작성
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/38d57386-325b-4627-a7b0-60f343169837">
</div>

3. GitHub에서 Submodule에 대한 수정사항 커밋이 발생
   - Main-Project에서 업데이트
```
git submodule update --remote
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/7d3fc7ef-6724-4dd8-b507-37fcff45f903">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/a5d75cf5-bc78-4a84-a64c-093d0d8adeed">
</div>

  - submodule 안의 또 submodule이 존재하여 모두 Update 하고 싶을 때 : 위 명령어 끝에 --recursive 추가

 
