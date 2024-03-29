-----
### Soucre Tree 에서의 Branch / Merge / Rebase 예제
-----
1. 메뉴 상단의 '브랜치' 생성 / 커밋은 왼쪽 상단 이용
2. main branch에서 practice1.jsp의 내용을 바꾸고 commit
3. to-merge branch에서 practice1.jsp의 내용을 다시 바꾸고 commit
4. to-merge branch에서는 practice1.jsp의 내용을 새로 추가하고 commit
5. 현재 source tree 상태

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/df38e243-5189-41ad-a619-cd01a9cae927">
</div>

5. merge 방법
   - merge의 주체가 될 branch 선택 (여기서는 main branch)
   - 그리고 merge가 될 branch에 대해 다음과 같이 설정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0228862b-d477-4e02-9a36-ed05a569a21b">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3ec1d85f-2711-4dfd-bae1-253a2d10da3e">
</div>

6. rebase 방법
   - rebase는 rebase할 branch로 이동 후 속할 branch에 대해 rebase
   - 다음과 같이 설정
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c70562b4-e75f-4bd2-94c1-1b495122ecb1">
<img src="https://github.com/sooyounghan/Web/assets/34672301/541adb1c-ca43-4785-9dd3-32d6409d208b">
</div>

  - main branch를 to-rebase 앞으로 fast forward 후, 사용하지 않는 branch 제거
<div align="center">
<img  src="https://github.com/sooyounghan/Web/assets/34672301/fa604cbc-e640-4558-8657-6da0575ad260">
</div>

-----
### Soucre Tree 에서의 Conflict 예제
-----
* rebase는 충돌 가능시 되도록 CLI로 진행하는 것이 좋음
1. main branch : practice2.jsp에 내용 추가
2. conflict branch : practice2.jsp에 내용 추가
3. main branch에서 conflict branch를 병합하면 병합 충돌 발생
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/afd5ae6e-1547-49f7-9648-668197b5dc44">
</div>

5. 이러한 충돌이 있으므로 바로 병합을 commit하지 않고, 충돌을 해결될 때까지 기다림
6. 해당 문제를 해결한 후 커밋해준 뒤, 다시 병합하면 해결
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/200d9958-dd35-4119-b3c6-e8fa734bd1ba">
</div>
