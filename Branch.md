-----
### branch
-----
1. 분기된 차이 = '다른 차원'
<div align = "center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9277c3fa-f793-4c91-876f-322afa727f93">
</div>

2. 즉, 프로젝트를 하나 이상의 모습으로 관리해야 할 때 사용
   - 예) 실배포용 / 테스트서버용 / 새로운 시도 등 다양하게 적용해야 할 때를 생각
     
3. 여러 작업들이 각각 독립되어 진행될 때 (가장 많이 이용하는 목적)
   - 예) 신기능 1, 신기능 2, 코드개선, 긴급수정 등..
   - 각각의 차원에서 작업한 뒤 확정된 것을 main branch에서 통합
  
4. 중요사항은 이 모든 것이 '하나의 프로젝트 폴더'에서 진행되는 것!

-----
### branch 생성
-----
1. branch 생성
```
git branch add-pratice
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5ba9a79b-f3ef-48e9-96a0-47120b99b26e">
</div>

  - branch를 생성한 것이지, 아직 이동한 것은 아니므로 현재 main branch

2. branch 목록 확인
```
git branch
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ab4d2f12-423f-4cca-ac37-d298337725b0">
</div>

  - main 앞의 *는 현재 branch의 위치
    
3. branch 이동
```
git switch add-practice
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/02c1e8e9-9ce8-4101-9e37-36f88fc0619c">
</div>

  - 현재 branch가 add-practice로 이동
  - SourceTree로 확인하면, 현재 main / add-practice branch가 나눠졌지만 아직 같은 버전에 위치하고 있으므로 분할되지 않음 
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5d8b848e-bcfb-4d67-8ed0-620e5c822d20">
</div>

      - 기존에는 checkout 명령어 하나로 사용했으나, Git 2.23 버전부터 switch, restore로 분리
      - branch 간 이동은 switch 사용하도록 변경

-----
### branch 생성과 동시에 이동 / 이름 바꾸기
-----
: 다시 mian branch로 이동하여, 이번엔 now-practice branch 생성과 이동을 동시에 하도록 해보자.
```
git switch -c now-practice
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/406fd2f9-7321-412f-8373-81bbb5e35702">
</div>

  - 다음과 같이 now-practice branch로 분기 이동한 것을 확인할 수 있음
  - 기존에는, git checkout -b "branch_name"

-----
### branch 이름 바꾸기 / 삭제
-----
1. to-deletet branch 생성 후, to-erase로 이름 변경
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2df65e07-236c-494f-99c6-1e8143c9ad4b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/850e2236-cd85-41f2-b60c-c96766c3f86e">
</div>

2. 현재까지 상황에 대해 source tree를 확인해보자
<div align="center">
<img  src="https://github.com/sooyounghan/Web/assets/34672301/61ca3a89-0cef-41ee-8c21-d402b7e7032d">
</div>

3. to-erase branch 삭제
```
git branch -d (삭제할 branch명)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e61e7662-4af6-4b25-947e-9f79ecfc8b74">
</div>

  - 지울 branch에 다른 branch로 적용되지 않은 내용의 커밋이 있을 시에는 -D 옵션으로 강제 삭제
```
git branch -D (branch_name)
```

-----
### branch 예제
-----
1. main branch에서 다음과 같은 작업이 실행 후, 커밋 작업
   - practice1.jsp 내용 수정 (내용 : insert)
   - practice2.jsp 내용 수정 (내용 : Hi insert)
    
2. add-practice branch에서 다음과 같은 작업 실행
  - practice4.jsp 내용 수정 (내용 : practice branch..)
  - practice5.jsp 내용 수정 (내용 : practice branch..)

3. now-practice branch에서 다음과 같은 작업 수행
   - pracitce1.jsp 내용 수정 (내용 : insert now-practice)
   - practice4.jsp 내용 수정 (내용 : insert now-practice)
   - pracitce6.jsp 추가

4. main branch에서 practice5.jsp 내용 변경

5. now-practice branch에서 practice6.jsp 내용 변경
   
6. 위 단계 까지 완료 후, 먼저 source tree를 보면, 세 개의 분기가 나눠진 것을 제대로 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d9cee673-9bf7-4f6d-a0f4-a999927fd03e">
</div>

  - 첨언하자면, 현재 이클립스 내에서는 정확히 확인이 불가능한데(refresh 자주 해주기), source tree로 접근해서 확인하면 분기마다 변경된 사항을 편하게 볼 수 있음

-----
### 여러 branch의 내역 편리하게 보기 
-----
```
git log --all --decorate --oneline --grpah
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/20a39ab8-679f-4938-bd0a-52b9c971126c">
</div>

  - * 는 하나의 branch
  - 분기별로 나타내는 것을 볼 수 있으며, 현재 branch 위치도 파악 가능
  - 하지만 되도록, source tree로 편하게 GUI로 보는 것이 좋음

