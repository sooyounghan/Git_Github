-----
### branch 간 충돌(conflict)
-----
1. 파일의 같은 위치에 다른 내용이 입력된 상황
2. 상황 형성
  - 가장 처음의 main branch에서부터 시작 하도록 하자
  - main branch : practice1.jsp / practice2.jsp / practice3.jsp 생성 후 내용 수정
  - conflict 1 branch를 생성 후, practice1.jsp의 내용 수정
  - conflict 2 branch를 생성 후, practice2.jsp의 내용 수정 (1차 commit)
  - conflict 2 branch를 유지하면서, practice3.jsp의 내용 2차 수정 (2차 commit)
  - main branch : practice1.jsp / practice2.jsp / practice3.jsp 한 번 더 수정
  - conflict 1 branch : practice1.jsp의 내용 재수정
  - conflict 2 branch : practice2.jsp의 내용 재수정 (1차 commit)
  - conflict 2 branch를 유지하면서, practice3.jsp의 내용 재수정 (2차 commit)
    
3. 현재 상항에 대해 source tree를 보면,
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0adc3dfb-e3cc-4d7c-9dcb-634f0432b623">
</div>

4. main branch에서 conflict1과 merge하게 된다면?
   - 다음과 같이 conflict가 발생
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a8253f72-ba87-40a9-b32f-da77b4827823">
</div>

  - 즉, main branch와 conflict1 간에 서로 중복된 수정 부분에 대한 결정을 하지 못해 충돌 발생
  - 그렇다면, 실제 이 충돌이 발생한 practice1.jsp 파일을 보도록 해보면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1582ed1a-bfaf-4269-b7d3-4fc52cd6e259">
</div>

  - 이처럼, 현재 해당 파일에 conflict issue를 확인할 수 있음
  - 이 부분에 대해서,
    + main branch 내용을 유지하는 방법 (Accept Current Change)
    + conflict1 branch의 내용을 유지하는 방법 (Accept Incoming Change)
    + main과 conflict1 branch 내용을 모두 유지하는 방법 (Accept Both Change)
    + 아예 다른 내용을 입력도 가능
      
  - 우리는 이 부분에서 conflict1 branch의 내용을 살리고, 다시 한 번 merge를 진행해보도록 하자

  - 충돌을 해결한 뒤 기존과 동일하게 git add 후, git commit을 하면 자동으로 커밋 완료
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6e659a00-a649-4120-8292-9b4f7386f174">
<img src="https://github.com/sooyounghan/Web/assets/34672301/413b47e8-ef6b-4b36-8ede-a0592fe5e405">
</div>

5. source tree 현황 (conflict issue가 있던 main / conflict1이 merge된 것 확인 가능)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1632af4f-f5ae-4cfa-aca9-a7734fdf5235">
</div>

-----
### rebase 충돌 
-----
1. 위의 상황 조성에서 main branch에서 practice2 / 3.jsp 수정 후, conflict2 branch에서 동일한 파일에 대한 수정을 지속 반복
2. 해당 부분에 대해 rebase 충돌 발생
   - merge의 경우에는 두 branch에 대해 하나로 병합하는 것이므로 충돌 해결이 commit 1번으로 해결
   - rebase의 경우에는 main branch의 마지막에서부터 이동되어 연결되는 것이기 때문에 해당 충돌 해결에 대한 commit을 반복해줘야함 (즉, branch 안에 있는 모든 commit마다 충돌 과정을 차례대로 해결해줘야함)
  
3. 위의 상황에서 이제 rebase를 진행해보자
   - 먼저 conflict2 branch로 이동 후, rebase 진행하면 충돌 발생을 확인할 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/22cd271e-d733-4bd0-96c9-96265865abd4">
</div>

   - git staus로 확인하면, 다음과 같이 현재 두 branch에서 모두 수정이 들어가 충돌 발생을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/68e50e6c-2fd0-470e-82fe-311164ac05c6">
<img src="https://github.com/sooyounghan/Web/assets/34672301/51c77e71-aecb-4d9d-9e86-a121e8527a5e">
</div>

   - 여기서 우리는 conflict2 branch의 내용을 유지한 뒤 (충돌 부분 수정), git add
     + 이제, 해결 가능하므로 다음 명령어 사용 (한 번에 끝나지 않을 수 있기 때문에 한 단계 씩 rebase 진행)
```
git rebase --continue
````
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9d2877dc-541a-461d-ac9a-938ff0b352ca">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b8d0bb52-1f7a-458b-8caf-90621ce4f7d7">
</div>

  - 위 과정을 모든 충돌이 반복할 때까지 진행하면 됨 (위의 사진에서 1/4 rebase였으므로 총 4번 반복)

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b4486985-c99d-4af0-8684-95c173676e60">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3ac3e1af-7b48-4ffe-8c2c-efd20f3afd46">
</div>

  - 이렇게 rebase 충돌이 해결된 것을 확인할 수 있음
  - 추가적으로 rebase로 인해 main branch가 conflict2 branch에 비해 뒤쳐져 있으므로 처리
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1729b569-35b7-47cb-83f1-2833f1560636">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cdefd285-f4e9-433b-b289-e491dddb357b">
</div>

   - conflict1, conflict2 branch까지 제거해주면 완료 (branch를 지우지 않으면, branch가 많아져 혼란 야기)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6c213a10-0fd6-4b6d-83a5-eaa122f79156">
</div>

-----
### merge / rebase 중단 
-----
1. 그럼에도 불구하고, 중복되는 수정 내용이 너무 많아 merge / rebase 를 중단하는 것이 효율적이라면?
2. abort 키워드 이용
```
git merge / rebase --abort
```
3. merge가 중단되고 이전 상태로 돌아감 (rebase도 동일)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0bf95359-9402-49f1-a6d7-35cd14280540">
</div>
