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
<img src="https://github.com/sooyounghan/Web/assets/34672301/bee85b78-aa73-4f57-9eb3-1f63c38716a6">
</div>

5. push
   - local에서 practice2.jsp에 내용 추가
   - Source Tree에서도 현재 커밋되지 않은 부분임을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9928ec5f-d827-4b98-99bd-8dd66217313f">
</div>

  - 이제 Soruce Tree에서 커밋을 눌러주면, commit과 push를 동시에 가능

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/7e9744c2-a4f2-4dc4-8abd-4b9e81b9e024">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e6660845-49a6-426a-89ed-0d7b3be36828">
</div>

  - 적용됨을 확인 가능

6. pull
  - pracitce3.jsp에 내용 추가
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/79088660-7c96-45f4-be33-73e9869b1e31">
</div>

  - Source Tree에서 패치(Fetch)로 가져오게 되면, 다음과 같게 설정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/71dd5d31-ddc9-4309-bc7c-6fbe636b5324">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f0ae3a52-3342-4033-aad2-086af892d84b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/eb677abc-a43a-4299-b1a3-58565c15ecae">
</div>

  - 여기서 풀(Pull)을 선택하면, Pull을 할 때, 발생할 상황에 대해 rebase / merge 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d0484381-b751-4a97-8128-0f0e2bdbf6c3">
<img src="https://github.com/sooyounghan/Web/assets/34672301/53d61ff6-7541-4a2e-89fd-204ca3df1f5a">
</div>

7. branch
   - 메뉴 중 브랜치 선택 후, local-branch를 생성하면, 다음과 같이 생성
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/442cee51-8f35-484d-85c2-124b5f50a9fe">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5386843b-e5cb-4981-b910-fead863ed7d8">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e7108fd4-294a-4207-9f29-a0f864ee36e1">
</div>  


  - 이를 remote로 push하려면 다음과 같으며, 어떤 local branch를 push할 것인지 그리고 remote에 remote-branch로 생성 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3cd421e0-bb6a-4b34-b182-a74e4ea5ebab">
<img src="https://github.com/sooyounghan/Web/assets/34672301/abcfd738-6f22-482b-9526-9e765bb62564">
</div>

  - 반대로 remote에 from-remote를 만들고, 이를 local로 가져오도록 해보자. remote에서 생성 후, Source Tree에서 패치하면 등장
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9eab2efa-77f6-4a4c-afbe-84d2624ac0f7">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a411f4bd-e9b8-4c45-87c2-c0af23bd6241">
<img src="https://github.com/sooyounghan/Web/assets/34672301/716e8352-4d92-43d0-8744-82f00b5beff1">
</div>


  - local로 가져오기 위해서는, 해당 원격 branch에 대해 다음과 같이 설정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/847fc813-dec4-4219-b44a-7d5254364275">
<img src="https://github.com/sooyounghan/Web/assets/34672301/94cc7ff6-c851-4a99-a2f8-9f4795c0563c">
</div>
