-----
### VCS (Version Control System) = 버전 관리 시스템
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/810d3a35-6246-4126-aadf-9191e0b7f038">
</div>

1. 프로젝트의 시간과 차원을 관리
2. 프로그래밍을 해서 결과물을 만드는 것 = 새 기능을 넣고 오류를 수정하고 성능을 개선하여 새로운 버전
3. 하지만, 진행 과정에서 취소의 문제가 발생에 대한 해결 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/28db689a-4b7b-41eb-8151-e560445e007a">
</div>

  - 과거 : 버전마다 압축 또는 이동식 디스크를 이용해 수동적으로 이동

4. 더불어, 현재 진행중인 코드에 대해 프로젝트 파일에 넣어 그것을 수정해보고 싶다면?
  - 과거 : 사본을 만들어 제작 (용량과 변경사항을 모두 하나하나 확인해서 가져와야 함)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/97428606-4752-438a-9a97-3887e3449a9a">
</div>

5. 즉 git은 프로젝트 폴더를 복사할 필요도, 압축할 필요가 없음
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d27449dd-a2ce-49f1-a13b-85e33ebd28ad">
</div>

6. 더 나아가, 프로젝트 버전을 언제든 되돌릴 수 있고, 프로젝트 내용을 다른 폴더 인 것 처럼 여러 모드로 자유롭게 전환 가능, 변경사항을 쉽게 변경 가능

-----
### Git Bash
-----
1. Git 사용에 필요한 터미널
2. 리눅스/유닉스에서 사용되는 CLI 명령어들을 윈도우에서 사용 가능
   
-----
### Source Tree 설치
-----
<div align="center">
<img src ="https://github.com/sooyounghan/Git-Github/assets/34672301/dc4b54ec-60e4-4ac7-8065-8623b06185e7">
</div>
1. Git을 GUI로 다룰 수 있도록 해주는 Tool
2. Bitbucket / Mercuiral
   - Bitbucket : Github과 같은 종류의 서비스
   - Mercuiral : Git과 같은 다른 프로그램

-----
### Git Bash Version
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d33b2aff-4b2e-457b-a683-44ad8c662d12">
</div>

: 버전 확인 : git --version

-----
### CLI / GUI
-----
1. CLI(Command Line Interface) : 명령어 기반 인터페이스 (Git Bash)
   - 뭔가를 실행하기 위해 어떤 명령을 내릴 때 사용하는 것이 좋음
2. GUI(Graphic User Interface) : 유저가 사용하기 편하도록 그래픽 요소를 활용한 인터페이스 (Source Tree)
   - 프로젝트의 상태를 Git 상에서 자세히 살펴보고 싶을 때 사용하는 것이 좋음

-----
### Git 최초 설정
-----
1. Git 전역으로 사용자의 이름과 이메일 주소를 설정 (이는 Github 계정과는 별개)
   - 설정하는 이유는 이 git을 나중에 사람들과 협업할 때도 같이 쓸 때, 어떤 작업을 누가했고, 어떻게 연락할 수 있는지 설정하기 위함
2. 터미널 프로그램(Git Bash 등)에서 아래 명령어 실행
```git
git config --global user.name "(본인 이름)"
git config --global user.email "(본인 이메일)"
```
   - 프로젝트마다 다르게 설정 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/89959e67-b3ab-4147-8a33-b23a33addd5d">
</div>

3. 확인 방법
```git
git config --global user.name 
git config --global user.email 
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/a376d1b8-46a2-42e7-8439-cb009519045f">
</div>

4. 기본 브랜치명 변경
   - Git의 기본 Branch 이름 : master > main
   - 부속적인 Branch의 이름 : slave > trunk
     * 첨언하자면, master-slave, 즉 과거 흑인 노예와 그들의 주인을 연상시키는 단어라 요즘은 변경하려는 추세라고 함

```git
git config --global init.defaultBranch main
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/8c95e991-9c12-4b88-8011-9f7d07f16ac3">
</div>

-----
### 프로젝트 생성 & Git 관리 시작 (보기 쉽게 git_practice로 프로젝트를 진행 예정)
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/2d370eb9-1fed-4376-b8c6-2d9a085ab44f">
</div>

* pwd로 현재 git bash의 위치를 확인한 후, 자신이 원하는 파일의 절대경로를 cd 명령어를 사용해 이동
* 여기서는 C:\Users\lxx._.han\Desktop\git_practice 위치에서 시작할 예정
1. git_practice는 프로젝트의 최상위 폴더
2. git init을 통해 기본 Local Repository를 설정

<div aling="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/3e885130-19cc-4770-a89b-787211f2cc77">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/365f2876-665c-4b09-bb17-79c598413277">
</div>

  - 주의 : 폴더에 숨김모드 해제를 통해 .git 폴더 생성 확인
  - .git은 진행하고 있는 프로젝트의 관리 내역을 맡아주는 역할 담당 시작
  - .git 폴더를 지우면, git 관리 내역은 삭제 (현 파일들은 유지)

3. 이제 이 프로젝트에 임시 pratice.jsp와 practice2.jsp를 생성
   - 현재 아이콘 옆에 뜨는 ?는 쉽게 말해, git과 연동이 되었으나 커밋을 아직 올리지 않아 모르는 파일이나 폴더에 물음표가 뜨는 것임
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/624c6147-4393-418b-bc87-79ef596bd8a7"> 
</div>

-----
### git status
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/3a292fae-2c3d-42a3-bc68-fba5cc7046c7">
</div>

  - git status는 말그대로, 현재 지정된 폴더에서 현재 폴더의 상황을 'git'의 관점으로 보여주는 것

-----
### Source Tree 관점에서 접근
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/95da7a32-01de-4a21-90aa-d10e16452c98">
</div>

1. 최상위 루트 폴더에 저장된 폴더를 Source Tree에서 접근하도록 설정
2. 이에 접근하게 되면 다음과 같이 정보가 나옴
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/cc18e2a0-caf5-47e2-be3f-fc81c8123719">
</div>

3. 삭제 시에는 git이 관리하기 원한다면, 북마크만 삭제
4. Source Tree 관점에서 git이 관리하는 저장소 만들기
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/be8c462d-72e8-4829-ba60-4e5763dd5682">
</div>
