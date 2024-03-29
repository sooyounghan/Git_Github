-----
### 원격 저장소 (Remote Repository) 이용
-----
1. 우리가 기존에 연동했던 git의 관리하는 부분을 우리가 새로 생성했던 Git_Practice에 연동을 해보도록 하자!
2. 즉, Git_Practice Remote Repository에 해당 git이 관리하는 부분이 올라간다고 생각
3. 다음과 같이 https가 설정하도록 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a389bd89-463f-4f44-8744-ab271414086c">
</div>

4. 그 다음 아래 부분을 보면, 두 개의 옵션이 존재
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4bd865a1-1382-4e7f-a277-cb0994e71dab">
</div>

  - "create a new repository on the command line"은 로컬 컴퓨터에서 새로운 깃(Git) 저장소를 생성하는 작업을 의미
    + 즉, 로컬 환경에서 깃 명령어를 사용하여 새로운 프로젝트를 시작할 때 사용
  - "push an existing repository from the command line"은 이미 로컬 환경에 존재하는 저장소를 깃허브(GitHub)나 다른 원격 저장소로 밀어넣는 작업을 의미
    + 즉, 로컬 저장소의 변경 내용을 원격 저장소로 업로드하는 것이 포함
   
5. 이미 기존에 관리하던 git을 연동시킬 것이므로 두 번째 옵션으로 진행 예정이므로 이를 복사한 후, git과 연동된 부분에 대해 해주면,
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/57fd45b4-b0d3-4602-9b8b-a6e93454e267">
<img src="https://github.com/sooyounghan/Web/assets/34672301/22698c87-81c9-40ba-8092-cd1ed3cce745">
</div>

  - 다음과 같이 Remote Repository에 해당 git이 연결되었음을 확인할 수 있음

6. 그렇다면, 이제 5번에서 진행했던 명령어에 대해 알아보도록 하자.
```
git remote add origin https://github.com/sooyounghan/Git_Pracitce.git
```
  - 해당 명령어는 Local Repository의 Git 저장소를 Remote Repository로의 연결을 추가하는 것을 의미
  - 원격 저장소 이름에 흔히 origin을 사용하나, 선택에 따라 다른 것으로 수정 가능 (협업하는 사람의 입장에서는 GitHub 저장소로부터 받아오는 입장으로 origin. 즉 출처가 이곳임을 되도록 설정)
  - SourceTree에서도 확인하면, 원격에 Origin이란 이름의 공간이 추가되었음을 볼 수 있음

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8487ddab-c20a-4e87-9f1b-82517396e9e1">
</div>

```
git branch -M main
```
  - GitHub에서 main branch의 이름을 설정


```
git push -u origin main
```
  - Local Repository의 Commit 내역들을 원격으로 push(즉, 업로드 하는 것)
     + push : 현재 내 컴퓨터에 있는 commit 내역들을 Remote Repository에 올리는 행위
  - -u 또는 --set-upstream 
     + 현재 지역 저장소에 속한 branch의 이름은 main
     + 이 main branch를 push를 할 때, 이를 어떤 원격 저장소와 그리고 그 원격 저장소의 어떤 branch에 push할 것인지를 Setting 하는 것

  - 따라서, 이후 git push 명령어를 입력하면 무조건 main에서의 push는 origin의 main branch로 push
  - 그렇다면 설정하는 이유는? 한 프로젝트의 원격 저장소가 여러 개 일 수 있으므로 이를 명확하게 하기 위함

7. 또한, 연동된 원격 저장소에서 다음과 같이 commit된 것과 시간 / 내역들 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d9c0c0fb-3f71-4265-8890-b94d185f13a2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ec9496eb-1a25-4002-9b8a-e00878ba3718">
</div>

-----
### 원격 저장소 (Remote Repository) 확인
-----
```
git remote
```
: 현재 연결된 원격 저장소를 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/923e4de6-c6eb-4cc6-9f64-f00147b57a62">
</div>
  
```
git remote -v
```
: 자세한 내역 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d4ee61d9-1ab8-4b99-b88f-dd9578ac3d31">
</div>
  
-----
### 원격 지우기
-----
```
git remote remove (origin 등 원격 이름)
```
: 원격 지우는 것 (= Local Project와의 연결을 없애는 것 / GitHub의 Repository는 지워지지 않음)

-----
### GitHub에서 프로젝트 다운
-----
1. Download ZIP : 파일들만 다운 받음 (Git 관리내역은 제외) [협업하는 방식은 아님]
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6e3a4b1f-2986-4303-8e8d-0aaf80eee364">
</div>

2. Git Clone : Git 관리내역 포함 다운로드
  - Project를 다운받기 원하는 폴더로 이동 (여기서는 C:\Users\lxx._.han\Desktop\Practice_Project로 할 예정)
  - 해당 폴더에서 Open Git Bash Here로 진입
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3ebd7f53-96e2-4c9e-938a-cd589db46d54">
</div>

  - GitHub의 원격 저장소에서 해당 주소 복사
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/00508ded-a9c0-4ad8-88bf-c08ff5d0848c">
</div>

```
git clone (원격 저장소 주소)
```

<div align="center>
<img src="https://github.com/sooyounghan/Web/assets/34672301/ba03610c-b300-4abb-9114-daebfc8d7974">
</div>

  - Cloning의 의미 : Remote Repository의 모든 것, 즉 파일 뿐 아니라 git의 관리 내역까지 모두 복사하는 것

<div align="center>
<img src="https://github.com/sooyounghan/Web/assets/34672301/02036631-4791-4e4e-91d8-5196b29485de">
</div>

  - 복사가 된 것을 확인 가능

-----
### Eclipse에서 Clone된 내역 가져오기 - 사전에 저장한 원격 저장소 Clone Directory 이용
-----
1. Eclipse - File - Import로 진입
<div align="center">
<img width="315" alt="1" src="https://github.com/sooyounghan/Web/assets/34672301/79a1cb81-abc0-4998-998b-782f11ba3c06">
</div>

2. 다음과 같이 Git에서 Cloning을 받는 방법이 두개 존재한다. 우선, 사전에 저장해서 이미 존재하는 Clone git File을 불러오는 방법을 보자
<div align="center">
<img width="420" alt="2" src="https://github.com/sooyounghan/Web/assets/34672301/d86082ec-e4df-48b7-8b25-dc801813ced0">
</div>

3. 해당 부분에 대해 Next를 하면, 다음과 같이 뜰텐데, 여기서 add를 눌러 우리 저장한 폴더를 불러온 뒤, Next를 누르자.
<div align="center">
<img width="355" alt="3" src="https://github.com/sooyounghan/Web/assets/34672301/421f9c2a-01cd-4f3c-9de2-da2c9f1a0e06">
</div>

4. 다음과 같이 창이 뜰텐데, 확인 후 Next
<div align="center">
<img width="443" alt="3-b" src="https://github.com/sooyounghan/Web/assets/34672301/06d90e1e-98f7-4dd4-a980-0618205bd6a4">
</div>

5. 역시 확인 후 Next
<div align="center">
<img width="347" alt="3-c" src="https://github.com/sooyounghan/Web/assets/34672301/bb66fa7c-5193-41c5-b971-aad37cfa247d">
</div>

6. 5번과 동일
<div align="center">
<img width="355" alt="3-d" src="https://github.com/sooyounghan/Web/assets/34672301/7efacb91-e07d-4e8a-b794-ed5c0758d43d">
</div>

7. 해당 부분은 이제 어떤 파일들을 불러올 것인지 체크하는 부분인데, 확인 후 Finish를 누르자.
<div align="center">
<img width="368" alt="3-e" src="https://github.com/sooyounghan/Web/assets/34672301/20437a0a-409d-4472-89d4-0fb3f9bc599b">
</div>

8. 결과를 보면 좌측에 다음과 같이 원격 저장소에 원격 저장소에 Clone된 git 결과물이 들어온 것을 확인할 수 있음
<div align="center">
<img width="341" alt="3-f" src="https://github.com/sooyounghan/Web/assets/34672301/bb07b13a-3b01-42c8-bef4-d73e2eb53bf7">
</div>

-----
### Eclipse에서 Clone된 내역 가져오기 - 원격 저장소의 URL을 활용해 가져오기
-----
1. Eclipse - File - Import로 진입
<div align="center">
<img width="315" alt="1" src="https://github.com/sooyounghan/Web/assets/34672301/79a1cb81-abc0-4998-998b-782f11ba3c06">
</div>

2. 이번엔 선택한 메뉴를 누르면?
<div align="center">
<img width="419" alt="4" src="https://github.com/sooyounghan/Web/assets/34672301/847b12ba-e4cb-456e-b9e3-175ebf70d546">
</div>

3. URL이 필요할텐데 이는, 우리가 아는 그 방법으로 주소를 얻어오면 됨
<div align="center">
<img width="406" alt="4-c" src="https://github.com/sooyounghan/Web/assets/34672301/f552bb09-a12c-422d-b2e8-9393e502f955">
<img width="276" alt="4-b" src="https://github.com/sooyounghan/Web/assets/34672301/1f5438c3-ef1a-47a3-a61f-51ab36265d68">
</div>

4. 확인 한 후에 진행하면, 마지막 화면이 나오고 Finish를 누르면 연동 완료 (현재는 이미 위에서 작업해서 들어왔으므로 중복되어 제한)
<div align="center">
<img width="392" alt="4-d" src="https://github.com/sooyounghan/Web/assets/34672301/99faac83-e1fc-4b79-88d8-9f10b6a1af62">
<img width="393" alt="4-e" src="https://github.com/sooyounghan/Web/assets/34672301/ed04cd25-ac39-4c18-8da6-efa2c281e9f9">
<img width="391" alt="4-f" src="https://github.com/sooyounghan/Web/assets/34672301/3b5d3a2a-d262-4d4f-90b4-8b4b9d1f505d">
<img width="706" alt="4-g" src="https://github.com/sooyounghan/Web/assets/34672301/0c6a048c-8615-485e-9373-76f109d39ae4">
</div>
