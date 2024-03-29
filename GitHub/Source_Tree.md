-----
### Source Tree 
-----
1. 저장소 - 원격 저장소 추가
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/259d3f8a-536f-4014-9142-c242c5b117b0">
</div>

2. 추가 버튼을 통해 진입
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/9753a0e0-2c01-42ab-8fd6-2f1f62bf2ef2">
</div>

3. 원격 이름에 설정한 GitHub Repository / URL 경로는 해당 경로
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/587f3741-a913-4839-801f-ff1f31084a15">
</div>

4. 완료가 되면, 위의 '푸시'를 누른 후 해당 부분을 누르고 push를 하면 연동
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/f1536274-2e6a-4869-9add-86bff9790718">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/e0f67266-d261-4c72-812e-57dc625826af">
</div>

5. push
   - local에서 practice2.jsp에 내용 추가
   - Source Tree에서도 현재 커밋되지 않은 부분임을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/9d5d6502-61c6-4b03-b717-4bf9e636961b">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/82f74ab4-7bff-4560-b82f-4bae257514de">
</div>

  - 이제 Soruce Tree에서 커밋을 눌러주면, commit과 push를 동시에 가능

<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/ae1aa293-767d-4e64-9326-d170cee0fb23">
</div>

  - 적용됨을 확인 가능

6. pull
  - pracitce3.jsp에 내용 추가
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/d4092487-a511-4b65-8dc3-47a5026a622e">
</div>

  - Source Tree에서 패치(Fetch)로 가져오게 되면, 다음과 같게 설정
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/fb1aa1c7-7fa6-4ff9-bc5a-a58b5064dca9">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/800cc2f1-e60e-406e-a173-2438df66f37f">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/db21a836-7cb0-4709-9774-ad82f7b26576">
</div>

  - 여기서 풀(Pull)을 선택하면, Pull을 할 때, 발생할 상황에 대해 rebase / merge 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/36bf6a5e-bb6b-4944-985b-74d4c3386177">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/b0baff73-aacb-41d4-af8a-171567b5d348">
</div>

7. branch
   - 메뉴 중 브랜치 선택 후, local-branch를 생성하면, 다음과 같이 생성
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/1fbc2670-cf58-423a-bd01-38d7466692ca">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/e6e31355-71d7-4348-aea1-e3d9860c24f8">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/5542475e-9920-4c1e-b9b7-c0aa25d9805e">
</div>  


  - 이를 remote로 push하려면 다음과 같으며, 어떤 local branch를 push할 것인지 그리고 remote에 remote-branch로 생성 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/feb1d6c1-1d94-4f55-b0e4-8bc2cf5d196e">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/f313a57d-256f-4772-a6b2-519fb7099e89">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/ef7c1b23-3d88-4774-af31-ffe48ea78b1f">
</div>

  - 반대로 remote에 from-remote를 만들고, 이를 local로 가져오도록 해보자. remote에서 생성 후, Source Tree에서 패치하면 등장
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/de7cdf5c-e430-419c-b1e4-a9426e0f59b3">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/5f1c09c4-c600-4de1-962c-c80641c5c7b8">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/dc899bdf-1074-4483-ac69-85c3c9dc04a9">
</div>


  - local로 가져오기 위해서는, 해당 원격 branch에 대해 다음과 같이 설정
<div align="center">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/0ba365c5-c514-4ffd-ab8f-67a7c8876ed4">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/dc520c06-03de-428e-97f3-2e2e8d512b32">
<img src="https://github.com/sooyounghan/Git_Pracitce/assets/34672301/0bc97c72-ae18-4d33-9a55-c03dac7995f3">
</div>
