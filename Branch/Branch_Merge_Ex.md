-----
### merge로 합치기
-----
* 사전 작업 : temp-branch 생성 후 practice7.jsp 생성
* 현재 분기 상태
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/317f2f3c-edac-4e51-a9a1-43018650ae73">
</div>

< temp-practice branch를 main branch로 merge >
```
git merge temp-practice
```
   - main branch로 선 이동
   - 위 명령어 실행
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/94a346db-8a51-4221-9c03-33f42a828920">
</div>

   - :wq로 자동 입력된 커밋 메세지를 저장하며 마무리 (맥)
   - merge 결과로 main branch 내로 temp-practice와 합쳐짐을 볼 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f0fd4311-b734-497a-91dd-b83c07aad924">
<img src="https://github.com/sooyounghan/Web/assets/34672301/18d48f1c-cde5-453e-a4a6-f63a2ee7c371">
</div>

-----
### merge와 reset
-----
1. merge는 하나의 commit 개념
2. 그러므로 reset으로 변경 가능
3. 실제로 특정 시점에 대해 reset하면 다음과 같이 변경
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/cbeee31a-87ad-4bae-9bf8-84cf98ae3227">
</div>

4. merge로 branch가 병합되면, 병합된 branch를 삭제하면?
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/668c238c-7d67-4600-8195-440eff0a4216">
</div>

-----
### rebase로 합치기
-----
1. rebase는 merge와 반대로 main branch가 아닌, sub branch가 기준이 되어야 함
   - 즉, sub branch를 main branch로 rebase 한다는 개념
2. new-practice를 main branch로 rebase 한다면?
```
git rebase main
````

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/35984c71-b727-408a-bc9c-dceedf03db5d">
<img src="https://github.com/sooyounghan/Web/assets/34672301/12fdae45-8450-40b7-a8f5-08f8bfbc17dc">
</div>

   - 현재 main branch의 위치와 new-practice의 위치가 서로 다름을 알 수 있음
   - rebase는 앞서 말했듯이, main branch의 분기 다음에 현재까지 작업한 new-practice의 작업을 병합하는 것이므로 위와 같이 나오는 것 (즉, main-branch가 현재 뒤쳐져 있는 상황)

3. main branch를 new-practice와 맞게 설정 하는 방법 (= merge 개념이라고 생각) [개념 헷갈리지 말기]
   - main branch로 이동
   - new-practice 시점으로 fast-forward 적용
```
git merge new-practice
```

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/652f2438-0179-475f-ae0d-e3eea20fe7e6">
<img src="https://github.com/sooyounghan/Web/assets/34672301/7dcfb8bc-4f48-44f8-9afa-20e8e79ee013">
</div>

   - main-branch와 new-practice의 분기가 일치 (해당 Logic은 추후에 다룰 예정)
   - 이에 따라, 이제 new-practice 삭제

< rebase 순서 >

4. 즉, rebase는 rebase를 할 대상 branch로 이동해 그 시점에서 main-branch의 뒤에 이어줌
5. 이 상태에서 new-practice를 main-branch에 merge

6. 실제 협업 과정에서 여러 추가적인 작업 / 실험 작업 / 급한 오류에 대해 각 다른 branch에 서 작업
   - 아니라면, 해당 branch 제거
   - 적용할 수 있으면 main 또는 sub-branch에서 merge / rebase 적용
