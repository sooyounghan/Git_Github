-----
### 델타 방식과 스냅샷 방식
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/26230a8c-6f47-4fc9-95ec-0bf6c6bbb00e">
</div>

1. 델타 방식
   - 각 파일이 생겨난 버전에 해당 파일 전체가 저장, 이후 이 파일에 수정이 가해질 때는 그 변경점들이 저장
   - 즉, 많은 양의 커밋이 존재한다면, 이 부분이 누적되어 처리되므로 속도가 매우 느림
   - 예를 들어, 버전 5 시점에서 C 파일의 내용은 버전 1의 원본으로부터 3번의 변화가 누적된 걸로 계산
  
2. 스냅샷 방식
   - 버전이 새로 만들어질 때, 해당 버전의 각 파일이 최종 상태 그대로 저장
   - 많은 양의 커밋이 존재한다 할지라도, 항상 최종본으로 유지하고 있으므로 속도가 빨라질 수 밖에 없음
   - 예를 들어, 버전 5의 경우 A파일은 변화가 없으므로 버전 4에서의 A파일을 그대로 연결해서 가져옴
   - 변화가 있는 B와 C 파일은 이 둘 각각의 최종 파일 내용이 그대로 저장

-----
### 중앙집중식 버전 관리와 분산 버전 관리
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0bbc0cc0-99dc-4464-b4a3-1ed99698556a">
</div>

1. 중앙집중식 버전 관리 (CVS, Subversion)
   - 원격 서버에 모든 관리 내역들이 저장
   - 로컬에는 중앙에서 현 버전 것만으로만 작업 가능
   - 즉, 원격 저장소에 의존적
    
2. 분산 버전 관리 (Git)
   - 로컬의 파일 뿐만 아니라 전체 Git Commit과 Branch까지 받아오므로 Local에서 자유롭게 적용 가능
   - 즉, 모든 구성원들이 Git의 상태까지 공유하므로 각자 편한대로 작업하다가 원하는 때에 프로젝트를 Push / Pull 로 협업 가능
     
-----
### Git의 강점
-----
1. Snapshot 이용
   - 일반적인 VCS는 '델타 방식'을 사용

2. 분산 버전 관리

-----
### Git의 3가지 영역
-----
<div align="center">
<img src = "https://github.com/sooyounghan/Web/assets/34672301/72ced2c4-5291-4ccf-9a3d-b5c56ebcd0f9">
</div>

1. Working Directory
   - 새로운 파일이 추가되거나 기존 파일이 변경되거나 삭제되거나 등의 수정사항이 만들어지는 존재하는 곳
   - git add 명령어로 Staging Area로 이동
   - 즉, 이처럼 어떠한 변경이 발생하는 것
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/46605623-de1c-4402-bdad-5320af3f78ca">
</div>

   < 두 가지 상태 >
   - Untracked : .gitignore에 추가된 파일이거나 add된 적이 없는 파일
   - Tracked : add된 적이 있고, 변경내역이 있는 파일 (즉, commit되어 Repository에 들어간 후, 수정사항이 발생하면 tracked 파일로 Staging 기다림)
     
2. Staging Area
   - Commit을 위한 준비 단계 (예) 작업을 위해 선택된 파일들)
   - git commit 명령어로 Repository로 이동
   
3. Repository (= Git Repository)
   - Commit들이 저장되는 곳
   - .git directory라고도 불림


-----
### Git의 다른 기능
-----
1. git rm
   - tigers.yaml를 삭제해본 뒤 git status로 살펴보기
      + 파일의 삭제가 working directory에 있음
      + 즉, 지워진 사실이 아직 add가 되지 않음을 의미
      + 버전에 저장하려면 commit 해야함 (또는 복원을 하기 위해서는 git reset --hard)
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/7262448d-b284-4d6a-8128-99de750baedc">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/ce3a4e58-3f06-4308-a167-c066c877d7c5">
</div>

   - 그렇다면, 위의 과정응 거치지 않고, 삭제가 되면 바로 staging area로 넘어가도록 하는 방법은?
   - git rm 이용
```
git rm 파일명
```

   - 따라서, tigers.yaml을 위의 명령어를 통해 삭제하면, 바로 Staging Area까지 진행된 것을 볼 수 있음 (즉, 바로 commit 가능)
   - 여기서도 git reset --hard로 복원 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/67ebd4c8-102e-49e8-8810-603e199cbdc9">
</div>

2. git mv
   - tigers.yaml를 zzamtigers.yaml로 이름변경 뒤 git status로 살펴보기
     + tigers.yaml의 삭제 감지
     + zzamtigers.yaml의 생성
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/267680f9-dc8d-411c-a4c5-35213222e871">
</div>

   - 여기서 zzamtigers.yaml을 git add 하고 git status를 해서 확인하면 rename를 인식
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/aca0e792-1e2d-492b-8e18-67bb5c436974">
</div>


복원 후 git mv tigers.yaml zzamtigers.yaml로 실행 뒤 비교
