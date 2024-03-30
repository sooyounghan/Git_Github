-----
### git rebase -i (interactive) 명령어
-----
```
git rebase -i (대상 바로 이전 커밋 [해시값])
```
1. 과거 커밋 내역을 다양한 방법으로 수정 가능
2. 명령어 정리
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5c8a59ef-0838-43d7-8df7-ae07fefe6370">
</div>

3. 예시
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ca7dc2f2-9607-469f-aea2-11b8ca5e534c">
</div>

  - 훗흥 이전의 커밋 수정 예정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f4116711-ada4-43d4-91c0-36066458ade8">
</div>

  - 홋흥 커밋을 '버그 수정'으로 변경 (r) / :wq!하면, 이름 변경으로 재진입 (훗흥 이전의 커밋에서 진입)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f0f56bc9-54b2-49e1-a5fc-543c88badd08">
<img src="https://github.com/sooyounghan/Web/assets/34672301/553b2ced-4efc-47f1-90b7-aac124cbec28">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a3339d8d-64ba-4ebc-bf46-866787c827d0">
</div>

  - 뻘짓 커밋 삭제 (d) (뻘짓 이전 커밋에서 진입)
  - 결전의 찜질방 항목 합치기 (s) : 첫 항목 뒤로 s 명령어 사용
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3994f37b-4126-4a48-a9d5-55356b7fe837">
<img src="https://github.com/sooyounghan/Web/assets/34672301/7dade0dc-3cac-4268-9e7b-1eaabe8141dc">
<img src="https://github.com/sooyounghan/Web/assets/34672301/707dc4f8-0dca-4132-be13-c4251df906d5">
</div>

  - 캐릭터 귤맨 추가, 시작메뉴 디자인 변경 두 작업을 두 커밋으로 분할 (e) (이전 커밋에서 시작)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/984aab6a-2a47-4acb-a0f1-799ca5409590">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d229c1c0-149b-4f36-bd4b-e6ce0067b07b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d54ea73a-1034-45b2-a706-645587efc4d8">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ef208e29-a7ce-4221-bf4e-0487e153081d">
</div>

  - 커밋 된 상태로 이동 : git reset HEAD^ (mixed 옵션)로, wroking directory 상태에 있도록 설정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/55cbcc34-cbfc-447f-82fe-b23a8c17c9db">
<img src="https://github.com/sooyounghan/Web/assets/34672301/aa04e3df-045f-4250-ba3f-9a419cf32ace">
<img src="https://github.com/sooyounghan/Web/assets/34672301/00058c54-062e-418f-b849-d1b58f5bd388">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9b6be153-eecc-48f1-a6df-216ecfd45d39">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6967a9c2-a86e-4cc6-951d-9de991b5c7ec">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e946b3a3-9fb8-4413-b0ce-7c69cd791283">
</div>


4. git은 순차적으로 commit이 저장
   - 과거 어떤 내역이 변경되면, 그 이후의 변경사항은 이전과 같은 commit이 될 수 없음
   - 즉, 과거 그 부분 수정이 아닌, 새로운 branch를 만든 후, 수정된 부분을 rebase로 연결하는 것을 의미
