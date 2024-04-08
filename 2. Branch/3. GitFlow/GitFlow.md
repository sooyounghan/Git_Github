-----
### GitFlow
-----
1. 협업을 위한 Branching 전략
2. 사용되는 Branch들
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5e888038-acf3-468c-b1d8-f75161fc848c">
</div>

3. https://nvie.com/posts/a-successful-git-branching-model/
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ed5b615d-c3e5-4e20-a0f1-00274b8411ce">
</div>

  - master : 실제로 user들에게 보여질 version들이 merge (tag)
  - develop : 개발 작업 부분
  - feature branches : 개발 작업 부분 중 굵직한 개발 기능 구현 부분 (따라서, 여러 개 가능)
    + develop으로 merge
  - release branch : develop branch에서 일정 완료가 되었을 때, QA 팀 등에 의해 검증하는 부분
    + develop / master branch로 이동
  - 개발 과정에서 발견된 부분은 develop branch 부분에서 가능하지만, 출시된 부분에 대해서는 당장 고쳐야하는 부분이므로 hotfix branch 이용

