-----
### Local에서 Branch를 만들어 원격에 Push
-----
1. Local에서 from-local branch 생성
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/08eaff77-5b73-4300-9845-bcc7082f45d7">
</div>

2. 여기서 git push를 한다면?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/da7c50b2-5b0e-48f3-8b2a-f3e984cdfc98">
</div>

  - git의 입장 에서 from-local branch를 어디에 push 해야되는지 모르는 상황 (즉, remote에 from-local을 명시해주면 좋겠다는 의미)
  - 그러기 위해서는 직접 명시하여 준비해달라는 의미
```
git push --set-upstream origin from-local
git push -u origin from-local
```

  - --set-upstream은 -u로 추격 가능
  - 즉, from-local branch의 대상 branch를 origin에 from-local branch로 정한 다음 push를 하는 것을 의미
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/8f359c47-8e44-4d05-b0f5-85f43784fd9b">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/60da628c-76c9-46eb-9044-a3e3b0f11d9d">
</div>

  - 이처럼, remote의 main branch 외에 from-local branch가 생성된 것을 알 수 있음

3. 이제 remote의 from-local branch로 접근해 practice2.jsp의 내용을 수정하면, 해당 원격의 해당 branch에서 변경된 사항
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/0d6ca9a9-7220-4ef8-842c-5791165129e6">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/5ed975c4-495a-40d3-84f4-e64fcf99d2e7">
</div>

  - 만약, main branch로 변경해보면, local-branch 내역이 반영되지 않음을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/ad92109c-516e-491e-b8f2-e9b25bb97fdc">
</div>

4. 그럼 local과 remote의 branch 목록이 어떻게 될까? (local의 branch : git branch)
```
git branch --all
git branch -a
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c2ada1f4-f47e-4c5e-a5c2-46ef3bddb5b5">
</div>

  - local과 remote 모두 branch 확인 가능
  - source tree에서 보면, 다음과 같이 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d5471bd8-e57b-4428-8f14-8eb52807470f">
</div>

-----
### Remote에서 생성된 Branch를 Local에 받아오기
-----
1. Remote에서 from-remote branch를 다음과 같이 만들자 
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/ec97ab44-946e-41ff-a9ef-2561c768b96a">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/e154bf91-5f10-4a1b-a371-bb55009f3d7c">
</div>

2. 즉, main으로부터 from-remote branch를 파생한다는 의미

3. 이제 local에서 git branch -a를 입력하면 어떨까?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/11eb0008-2c4c-4e27-a583-affbe46e251e">
</div>

  - 아직 local에 반영되지 않았음을 알 수 있음
  - 이유는 현재 local의 git이 remote의 변화들을 update받지 않았기 떄문임
  - git fetch 명령어를 사용하고, git branch -a로 확인하면, 원격의 from-remote branch가 local에 까지 적용된 것 확인 가능
```
git fetch
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/aae084f9-b1e1-462b-9368-53c8ff3e8019">
</div>

4. 그렇다면, 원격의 branch를 어떻게 하면, local branch로 받을 수 있을까?
```
git switch -t origin/from-remote
```
  - 즉, 원격의 branch에 대해 동일한 이름으로 local의 branch를 복사하여 연결하고, switch 함을 의미
  - 즉, 원격의 from-remote에 대해 local의 from-remote로 연결함을 의미 (git push -u와 비슷한 개념)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/93b7d031-1bf5-4d8b-8b8c-463fe850229b">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/8ec64e92-6cba-437f-9f0f-e50060f765ae">
</div>

  - source tree로도 확인하면, 생성된 것을 확인 가능

5. 사진을 보면, 위에서 remote에서 from-local branch에서 작업한 부분이 있을 것인데, 이를 이제 pull로 해서 받아보자(local의 from-local branch에 pull)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/b378016a-b34e-4cd0-bb5c-5b6248a04201">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c57e49e0-b181-424a-87e5-21237b787b78">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/0482bf0b-a5d5-4365-afe5-27c458a76956">
</div>

  - 다음과 같이 변경된 것을 확인할 수 있음

-----
### Remote Branch 삭제
-----
```
git push (원격 이름) --delete (원격 branch명)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/0c5095a0-f6c8-4644-b125-fbf260e59cae">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/10f49e7c-96d4-4dcd-83e3-84dd4843a700">
</div>

