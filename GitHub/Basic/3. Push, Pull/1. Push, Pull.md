-----
### 원격으로 Commit 올리기 (Push)
-----
*  Push : 나의 컴퓨터, 즉 로컬에서 GitHub 등의 다른 원격 저장소 서비스로 변화를 밀어 올리는 것을 의미

1. 우선 기존에 우리가 작업했던 지역 저장소에 다음과 같이 내용을 추가해보자.
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/fa626c80-069d-4f47-9eb0-fe2d0de26282">
</div>

   - practice1.jsp에 remote push! 라는 내용을 삽입 후 commit

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/54959a8c-971b-47b3-b117-a1bc0fb6d57a">
</div>

  - Soucre Tree로 현재 상태를 확인해보면, 현재 원격의 origin/main branch와 지역의 main branch가 있는 것을 확인 가능
  - 그리고 현재, 원격의 main branch가 지역의 main branch보다 뒤쳐져 있는 것을 확인 가능

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/aa7687cd-aac4-4681-b459-5d2f2b7c48fd">
</div>

2. 이제 이 로컬의 변화를 원격으로 보내보도록 하자. (즉, Push하는 것을 의미)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d3df1140-3b44-42d8-89ca-8b7e55da5bff">
</div>

  - 현재 원격의 practice1.jsp는 위와 같으며, 지역에서 마지막으로 설정했던 commit 내역으로 남아있음

3. 이제 git bash에서 다음과 같이 명령어를 입력하자
```
git push
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ab145579-2739-4c99-806b-79b2440d73af">
<img src="https://github.com/sooyounghan/Web/assets/34672301/dfc1b3b6-71c2-40b8-9644-d44f24d22db3">
</div>

  - 다음과 같이 push 작업이 진행되고, 원격에도 반영된 것을 확인할 수 있음
  - 추가적으로, 이미 git push -u origin main 대상으로 원격 branch가 지정되었기 때문에 가능

-----
### 원격의 Commit을 가져오기 (Pull)
-----
* Pull : 원격의 Commit(즉, GitHub에 존재)을 지역 저장소로 당겨오는 것

1. GitHub의 practice1.jsp에 local pull!을 추가하고, 저장하면, Update practice1.jsp Commit 저장
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/884c2dae-d0c6-4beb-8b16-c86ec0628a1b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b6f254ad-ef11-4a17-942c-7389e3ea6621">
</div>

2. Source Tree를 확인해보면, 지역 main에 대해서 원격의 Commit 내역이 없음을 확인 가능

3. 다음과 같은 명령어를 로컬에서 입력
```
git pull
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/689d3813-3b20-4464-b9ee-48df0d976a7b">
</div>

  - 다음과 같이 로컬에도 원격의 commit 내역이 반영된 것을 알 수 있음

-----
### 심화 : Pull 할 것이 있을 때, 만약 Push를 하게 된다면?
-----
1. 만약, 나의 commit에서 어떤 작업을 했고, 다른 팀원들도 작업을 해서 GitHub에 올린 상태
2. 즉, 나의 commit은 아직 반영되지 않았고, 다른 팀원들의 내용은 이미 원격에 commit이 된 상태라고 하자.
3. 먼저, 내 작업파일 중 practice1.jsp의 내용 중 main first update / conflict1-update / add3!을 main으로 변경하고 Commit을 했다고 하자.
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cb0550c0-5da1-4726-a14f-ff49d6e7f23d">
</div>


4. 그런데, GitHub에서 practice1.jsp에 대해 remote push! 내용을 remote push complete!로 수정했다고 하자
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/83ef5317-0f1c-4d05-9b41-dafd42ae9db5">
</div>

  - 즉, 이 상황은 먼저 이미 다른 팀원이 자신의 컴퓨터에서 작업을 완료하고 push한 상태와 동일

5. 그럼 현재 이 상황에서 push와 pull 모두 동시에 해야되는 상황에 부딪히는데, 이 떄, git push를 하게 된다면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9634d7ac-fb07-45d5-ac2f-a52f66b50122">
</div>

  - 에러 발생 : 현재 내 git 저장소가 원격 저장소보다 뒤쳐져 있으므로 발생
  - 그러므로 '항상 원격 저장소에 push를 하려면, 나의 내역이 원격 저장소의 최신 내역으로 맞춰져야함'
  - 즉, pull을 해야하는데, 현재 practice1.jsp에 대해 어느 부분을 맞춰줘야 할 것인가에 대한 문제 발생

6. 결과적으로 pull을 먼저 해야하는 것은 맞으나, 이 때 옵션이 두 가지 가능
  - git pull --no-rebase : merge 방식
    + 즉, 원격과 로컬의 main branch 각각 서로 branch로 보게 하여 branch를 나눈 다음 마지막 부분에서 합쳐지는 것을 의미
    + 즉, Local와 Remote의 어긋난 부분을 merge하는 방식
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/81abbfb7-6df4-4b01-a3c7-fa384a3067f1">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1fbb95ba-d56d-425b-9d75-aff40a1e92a6">
</div>

  - git pull --rebase : rebase 방식
    + 다시 분기되는 시점으로 reset
    + 결과적으로는 원격의 branch와 history를 맞춰야 하는데, debase 방식을 이용해 현재 local의 main branch를 원격의 main branch로 이동
    + 이 상태에서 git push 진행하면, 정상적으로 반영
    + 즉, remote에 맞춰서 remote에 local을 rebase하여 push하는 방식
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/01ba26fd-258e-4864-a2df-7edd3fa74dd9">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/bbdc0d39-1b1e-4a13-affb-89eb9a2f4b7e">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c3f1594f-7ee4-4504-ae17-c3dd50b34152">
</div>


  - 만약, 로컬의 commit 내역을 삭제하게 되면, rebase 방식에서는 원격의 정보만 받아오면 될 것이기 때문에 추가적인 rebase가 필요없음
  - 하지만, 원격의 commit을 받아오지 않고, 로컬의 commit 내역으로 진행한다면, 위의 rebase 방식과 동일함
  - 즉, rebase는 어떤 것을 선택하느냐에 따라 추가되는 커밋의 수가 달라짐

7. Local에서 rebase를 비추하는 것이지, Pull을 받는 상황에서 rebase를 하는 것은 괜찮음 (협업 시 사용 OK)

-----
### Local의 내역을 강제 Push (사용 권장 X)
-----
```
git push --force
```
: 즉, 강제로 Local과 Remote를 강제로 맞춘 것
