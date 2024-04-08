-----
### 다른 Branch에서 원하는 Commit만을 가져오기
-----
1. 현재 프로젝트의 구성도
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1e927ab0-0343-4bd2-a4b6-89b3a71530e1">
</div>

2. 다른 브랜치의 원하는 커밋 가져오기 : cheery-pick 명령어 사용
3. Cherry Commit을 main branch로 가져오기
   - main branch에서 실행
```
git cherry-pick (해당 커밋 해시)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8e545a5e-1182-4fc7-a523-250032ef3dbc">
<img src="https://github.com/sooyounghan/Web/assets/34672301/71c403c9-5c0d-407e-a6fe-ba376b61842c">
</div>

  - Fruit branch에 있던 Cherry Commit이 Main branch로 가져오게 된 것을 볼 수 있음
  - 즉, Merge와 Rebase와 달리, 단지 그 Commit을 복제해서 가져오는 개념 (두 Cherry는 다른 Commit)
  - 참고 : Source Tree는 항상 가장 최근에 실행된 Commit을 기준이 다음과 같이 보임
