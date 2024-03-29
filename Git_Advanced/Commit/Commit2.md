-----
### 보다 세심하게 Staging하고 Commit
-----
1. 내용을 확인하며 hunk별 Staging
  - Tigers 변경
    + manager: Thanos
    + coach: Ronan
    + 새 members: Gamora, Nebula

  - Leopards 변경
    + coach: Rocket
    + 새 members: Drax, Groot
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1c5a9153-2b6d-467a-864c-6f53966536d0">
</div>

2. 이러한 수정사항에 대해 하나씩 확인 (Hunk별 확인) 하여 add
```
git add -p
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6ba5e802-9078-43ba-b6b0-cab829cd8e85">
</div>

  - ?를 입력하면 명령어 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a7824a00-09a9-4200-9c83-d4118ca69905">
</div>

  - y의 의미는 하나의 hunk에 대해 받아들이겠다는 의미 = 즉, 하나의 파일에서도 나누어 일부분만 add 적용 가능
  - n의 의미는 한 hunk에 대해 받아들이지 않겠다는 의미

  - 일부분은 y / 일부분은 n로 설정한 뒤, git status로 확인하면, 두 개의 파일에 대해 staging / working directory에 모두 존재
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f5feeb40-fc04-404b-9b49-6fac52a3fa1f">
</div>
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/46961076-463c-4914-8559-5df2e360f795">
</div>

  - 즉, 부분적으로 add만 되었기에 발생

-----
### git commit -v
-----
1. 어떤 부분이 변경(변화)이 반영되었는지 보여줌
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/89067a96-a7da-4c78-b547-d1b36653497e">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1a717a91-ea7a-4cd7-bc44-1ac98baaf571">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e775b1ef-433a-40b3-97d7-6c01d41b73cd">
</div>

2. 변경사항을 확인하고 Commit 할 수 있도록 도와줌
  - commit을 하고, git status를 확인하면, 아직 staging 되지 않은 파일 부분만 존재
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ac9c156f-f485-4f1e-bd84-3a0355ba8b0b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1dfa1d47-180b-4807-9977-302c5f260bef">
</div>

3. 남은 파일도 add와 commit으로 처리하면, 2개의 Hunk로 나누어진 것이 모두 Commit 완료 
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/34550474-77b3-4abd-96d8-5ebcaf87a65d">
</div>

4. 즉, 같은 파일에 작성된 변경 사항도 분할되어 add / commit 가능
5. 즉, commit과 git diff --stage를 동시에하는 것

-----
### git diff --stage
-----
1. 현재 staging 영역에 존재하는 add된 파일들에 대한 변경 사항 확인 가능
2. 즉, Commit 될 파일들에 대한 변경사항 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c33f3bb7-a196-4a0b-9228-b6725a257aa5">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1d1528c2-9a29-437a-9f09-1904035f1c15">
</div>




