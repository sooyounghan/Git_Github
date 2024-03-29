-----
### git-heads의 현재 상태
----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/330dcf4b-16e3-4f70-a343-b5683dcf47c1">
</div>

-----
### Git의 HEAD
----
1. 현재 속한 Branch(해당 Branch)의 가장 최신 Commit
2. 즉, git-heads의 현재 HEAD를 Source Tree로 보면 다음과 같음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/41c2f483-1d86-4e9e-9785-537bf7562dc6">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cb8d6874-4bce-48bc-b789-6b1e7d4a15d9">
<img src="https://github.com/sooyounghan/Web/assets/34672301/be56aa68-f547-4fbe-be1a-43a3be34d684">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4371768b-28b9-4e76-afcb-2f4bfe2a302e">
</div>

-----
### Git의 checkout (Commit Hash로도 가능)
----
1. history 내역은 그대로 두고, 파일들의 상태만 옮기는 방법
```
git checkout HEAD^(~) (커밋 해시)
git checkout HEAD^(~)5 (커밋 해시)
```
  - 원하는 만큼 이전하고 싶다면 그 수만큼 ~나 ^ 사용
  - 또는 숫자를 사용해 이동 가능
  - 예) 3단계 전으로 이동 : git checkout HEAD^^^(~~~) 또는 git chekcout HEAD-3
    
3. delta-branch로 이동 후, 두 단계 뒤로 가고 싶다면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/10ee7dfc-f8f5-4c43-b4a3-22ff8a395cec">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8c9ebe6f-c945-43e1-b770-04ab1f695ca2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/61610e37-e23b-4219-baf9-22e929834c7b">
</div>

  - 사진과 같이 delta-branch의 두 단계 시점으로 이동
  - Source Tree에서도 HEAD가 두 단계 전으로 이동
  - 이 상태에서 한 단계 뒤로 또 이동하면, 다음과 같이 변경
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/de510ead-c41e-4a3b-824d-01f38373192d">
</div>

4. 단계 앞으로 이동 방법
```
git chekcout - 
```
: 한 단계 앞으로 이동함을 의미
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6d4095d9-0f80-418b-aade-5dbbee9e433e">
</div>


5. HEAD는 각 branch의 가장 최신 commit을 의미하는데, HEAD가 이동되는 것을 알 수 있음
   - 이 의미는, 결국 익명의 다른 branch를 생성해 이동하는 것을 알 수 있음
   - 실제, 아래 사진을 보면, 익명의 branch가 생성된 것을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/04aafb1a-4caa-4eea-925b-baf0a20ec7e2">
</div>

   - 즉 해당 시점 Commit에서 branch가 되어버린, 익명의 branch에 위치
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0ba64fb5-129d-4912-81bf-c4b73e64f68d">
</div>

6. 이 상황에서 다른 branch로 이동하려면, git switch로 이동 가능

-----
### Git의 checkout 한 후, 새로운 branch를 만들어 나누기
----
1. beta-branch로 이동 후, 한 단계 전으로 이동
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/69f500d2-5491-4ae5-a6d9-50e78f082159">
<img src="https://github.com/sooyounghan/Web/assets/34672301/05facc3c-6cbe-4f99-bfcf-01966bef1fbf">
</div>

2. 이 상황에서 gamma-branch를 만들어보면, 새로운 gamma-branch 생성
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a08d3d34-f144-44e5-95ec-41428e22a420">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5a42e19c-1fe9-47c9-ab9b-77da0c92b0f1">
</div>

3. gamma-branch에서 작업을 한 후, commit 후 확인하면 다음과 같음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8c07104b-727f-4281-8614-13a4680d2a6e">
</div>

-----
### Git의 HEAD를 이용한 reset
----
```
git reset (옵션) HEAD(원하는 단계) 
```
1. delta-branch 이동 후 2단계 이전 후 hard로 reset 하면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c70eb234-40a4-4c45-880d-8f472c8b84ff">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2535faff-d762-4916-bbd0-82a02810063d">
</div>

2. delta-branch에서 두 단계 이전 후 reset 된 것 확인 가능
