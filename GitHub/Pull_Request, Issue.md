-----
### Pull Request (PR)
-----
1. 변경사항을 Merge 하기 전 Review를 거치기 위함
2. 팀원들의 동의를 거친 뒤 대상 Branch에 적용
3. Pull Request 사용
   - 새로운 Branch 생성(develop branch) 후 변경사항을 Commit하여 Push
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ba973e7a-5720-427a-9310-0e21daa6d639">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1253a098-29ff-4442-9335-7003c8c10732">
</div>

   - GitHub Repository Page에서 Compare & Pull Request 버튼 클릭 (또는 ~ branchs에서 New Pull Request 클릭)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/96ae7e7b-d3ef-45a6-9748-84abec61c3b3">
</div>

   - develop branch에서 작성한 Commit 내역에 대해 Main Branch에 Merge될 수 있도록 Pull Request하는 것
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/73ca3b95-0298-415a-a0e5-ca7f4afccd5a">
</div>

   - 메세지 작성 후 Create Pull Request 클릭
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e0c20632-addf-4e99-b1e8-635e6299415b">
</div>

4. Pull Request 검토 후 처리
   - GitHub Repository 페이지에서 Pull Requests 탭 클릭
<div align="center">
<img src="https://github.com/sooyounghan/Git_Practice/assets/34672301/f8e8076c-f744-4cec-8e80-caee5db9d739">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e0c20632-addf-4e99-b1e8-635e6299415b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c5a7a204-aa99-4636-b935-2035b88928bc">
</div>

   - 대상 Pull Request 클릭해 내용 검토 (팀원이 올린 Pull Request에 대해 Comment와 Commit 내역을 통해 확인 가능)
     + 의견이 있을 시 코멘트 달기
     + 반려해야 할 시 Close Pull Request
     + 승인할 시 Merge Pull Request
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/333a5224-fe86-41c3-8657-378c431b2fcd">
<img src="https://github.com/sooyounghan/Web/assets/34672301/791d8bb5-1236-4511-80bf-79aced67c40d">
<img src="https://github.com/sooyounghan/Web/assets/34672301/73c0f523-81a8-442d-83f8-1b79f8db258e">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6bb8c41b-9ff6-483e-bace-214f8a602fa7">
</div>

  - Merge Pull Request 종류
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8e074f14-9a9c-4b32-b7f9-3353b283b60d">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3b816565-f889-40c9-895a-db2290abf986">
</div>

  - 승인에 따른 변화 (Main으로 Merge)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/77497762-9174-4d5f-aa97-2518b1551f9d">
<img src="https://github.com/sooyounghan/Web/assets/34672301/91781457-43cb-47d8-bad2-f0cb725d719c">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b9fc4b88-ecc5-4d92-9ed2-fa1410423c51">
</div>

-----
### Issue
-----
1. 버그나 문제 제보, 추가할 기능 등의 이슈 소통 (Open : 미해결, 해결 중 / Closed : 해결 완료)
2. 예시 : 네이버 지도 API 예제 (https://github.com/navermaps/maps.js.ncp/issues) / flutter(https://github.com/flutter/flutter)
3. 필요시 Label 또는 Milestone 생성
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4c8855b7-cadd-49a5-b848-2baff97fe1fb">
</div>

   - Label : 기존 라벨 사용 및 새로운 라벨 생성 후 사용 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4980993c-dcab-4e30-a6c1-521d98e32c69">
<img src="https://github.com/sooyounghan/Web/assets/34672301/bc15347f-d04a-4f19-961e-9d3c72bc1630">
</div>

   - milestone : 이슈의 주제 묶음 (특정 목표 등)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9803c326-8991-4cfc-8184-5f87196e09c7">
</div>

4. 이슈 작성 : 필요시 Label, Milestone, Asginee(처리 담당자 지정) 지정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/bedf4ae0-f00a-45c4-90cb-0a30d0a871d9">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1117a702-e9f4-486f-9afe-6ab2ff0e79b1">
</div>

6. 이슈 확인 후 처리
   - 코멘트 달기

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/57cb297e-4357-4139-8f1f-d1ef37bad698">
</div>

   - 관련 개발 착수 (Branch명이나 Commit Footer에 이슈 번호 반영 )
   - Label, Milestone, Asginee 수정 가능
   - 해결 뒤에는 'Close Issue'
