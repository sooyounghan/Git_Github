-----
### GitHub (OpenSoucre의 성지)
-----
* Git의 GitHub상 저장소는 배포용 Mirror 저장소 (참여 및 기여 불가)
  
1. 쉽게 생각하면, GitHub는 '코드 공유 및 협업 서비스'
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0ad9bcc9-a8e3-4ddd-9b6f-c2edf4485099">
</div>

2. 즉, 온라인 공간에 공유해서 프로젝트 구성원들과 함께 소프트웨어를 만들어낼 수 있도록 도와주는 서비스
3. 그렇다면 일반 클라우드에서 협업하는 과정과의 차이점은?
   - 일반적인 방법은 구성원들이 한 번에 한 명씩만 일을 하면, 하나의 작업에 대해 한 명이 수행
   - 그러면, 다른 팀원은 그걸 다시 다 다운 받아서 작업을 마치고, 또 업로드 하고 또 다른 팀원이 같은 반복을 수행

4. 일반적인 소프트웨어 개발 프로젝트에서는 하나의 프로젝트 폴더 내에서 같은 파일을 여럿 수정해야 하는 상황 다수 발생
   - 즉, GitHub는 이러한 부분에 대해 모든 업로드와 다운로드를 'Commit'단위로 주고 받음
   - 즉, 하나의 팀원이 자신의 부분에 대해 commit을 해서 버전을 만들고 업로드하면, github는 해당 버전으로 최신화
   - 다음 팀원이 완료한 작업을 commit해서 올리기 위해서는 위의 가장 최신화된 github 상 commit을 먼저 다운 받아 적용하도록 강제
   - commit 상 충돌사항이 있다면, 해당 부분에 대해 해결을 하고 비로소 자기가 작업한 부분을 commit해 업로드 가능

5. 핵심은 '자신의 컴퓨터에서 자신의 작업을 각자 원하는 때에 하되, 이를 공유하는 것은 Github라는 중간 매개체를 통해 중간에서 정리'
   - 서로의 작업에 대해 덮어씌어지는 등의 실수가 발생하지 않도록 편하게 협업이 가능하게 해줌
  
-----
### Personal Access Token 만들기
-----
1. 보안상의 이유로 채택한 방안
2. 프로젝트를 연동하기 위한 일종의 비밀번호를 따로 만드는 방법
3. 순서 (그림 참조)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/245a130c-7386-4263-9695-204238cd76c2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c29c5f0f-6061-404a-aa0f-a23b65b6d7e4">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cdcaa74a-144d-44d8-8347-4192cd59ef53">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f4c7079b-58b7-42cc-8be4-a4e69c889de2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/43bd6e35-45b1-48a7-8f50-2c308a8ca263">
</div>

   - Note : 일종의 자기의 token 이름
   - Expiration : 만료 기간
   - Select Scopes : 어떤 권한까지 이 Token을 허용할 것인가? (추후 수정 가능)
   - 중요! : 밑의 Generate Token을 하면, 토큰이 생성될텐데 이 페이지 한 번만 확인 가능 (복사해서 보관)

4. 컴퓨터 내에서 Token 설정 방법
   - 자격 증명 관리자 진입
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3645fe04-7eb7-4eef-8b71-6bec0312ecbf">
</div>
   - git:https://github.com를 찾아서 암호에 Token 저장
<div align="center">
<img width="587" alt="20240329_173522" src="https://github.com/sooyounghan/Web/assets/34672301/63923582-5e9b-4bfa-9fe8-17dd3040f276">
</div>

-----
### Source Tree에서 GitHub와 연동
-----
<div align="center">
<img src="https://github.com/sooyounghan/Programmers/assets/34672301/cdcc3fcb-dbbc-4552-8917-c6300286ff45">
</div>

<div align="center">
<img src="https://github.com/sooyounghan/Programmers/assets/34672301/77458b69-a591-46f1-8b1e-f0fa5cc528fd">
</div>

   - 해당 부분에 대해 편집으로 비밀번호 수정에 Token 입력

<div align="center">
<img src="https://github.com/sooyounghan/Programmers/assets/34672301/2a9fc398-fdde-40ab-a27e-e9f207414536">
</div>

-----
### 연습을 위한 새 Respository 생성
-----
1. 생성창으로 넘어오면, 다음과 같이 설정 (이름을 자유)
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/e960a3c9-3660-4787-a6b8-73bb6189c321">
</div>

2. 다음과 같이 등장하면, 성공적으로 완성
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/149198b9-79b3-468b-a03d-01ce115fed44">
</div>

3. 그렇다면, 해당 Repository에서 팀원들을 초대하는 방법은?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/80f8b43d-97ce-425e-894f-e7d29c7d599f">
<img src="https://github.com/sooyounghan/Web/assets/34672301/82dfab21-98b3-4990-9eee-e2d6b5065c72">
</div>

   - Git ID나 Email을 통해 초대 가능

