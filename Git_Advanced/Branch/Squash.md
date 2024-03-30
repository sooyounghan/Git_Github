-----
### 다른 Branch에서 파생된 Branch를 옮겨 붙이기
-----
1. 다른 커밋들을 하나로 묶어 가져오기
```
merge --squash (대상 브랜치)
```
2. root branch의 마디들을 하나로 묶어 main branch로 가져오기
```
git merge --squash (대상 브랜치)
```
  - merge가 완료된 것이 아닌, 이 branch들이 옮겨 붙여져서 add가 되어 현재 staging되는 것임
  - 따라서, commit을 해줘야 함을 주의
  - 또한, root branch는 기존 branch를 유지하며, 그 branch만 옮겨 붙여진 것
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f045b1c8-c679-4211-9a84-769bf36d8b00">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3f95b1da-7545-421d-9ec4-4ccedb4ac5b8">
<img src="https://github.com/sooyounghan/Web/assets/34672301/be65de2f-59a9-43c9-8007-35afcb3572df">
<img src="https://github.com/sooyounghan/Web/assets/34672301/82ce1cb8-0b67-463b-838f-d270144b51db">
</div>

3. 일반 merge와의 차이점
   - 실행 후 코드의 상태는 같지만 내역 면에서 큰 차이가 발생
   - 일반 merge : A와 B 두 branch를 한 곳으로 이어 붙임
   - merge --squash : B branch의 마디들을 복사해 한 마디로 모아 A branch로 붙임 (staged 상태)
