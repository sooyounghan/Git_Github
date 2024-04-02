-----
### GitHub Actions를 사용한 자동화
-----
1. CI/CD : 지속적 통합과 배포 (자동화와 관련)
   - 참고자료 :  https://www.youtube.com/watch?v=UbI0Q_9epDM 
   - Continuous Intergration (지속적 통합)
   - Continuous Deployment/Deliveery (지속적 배포)
   - 동종 : GitLab CI/CD, BitBucket Pipelines
   - 참고 자료 : https://www.yalco.kr/43_ci_cd/

2. GitHub Actions 살펴보기
   - github.io 페이지의 액션 (자동화로 인해 Action)
     + 해당 레파지토리 페이지에서 Actions Tab 살펴보기
     + 새로운 Commit Push 직후 다시 살펴보기

   - 다른 프로젝트에서 Action 추가해보기
     + Actions 탭에서 액션들 살펴보고 적용해보기
     + MarketPlace 살펴보고 적용해보기
     + Commit 후 Pull하여 Local에서 확인

3. 자동화 과정
   - 다른 Branch에서 작업을 한 다음, 원격의 Main에 Pull Ruest 요청
   - Test를 진행해 실패하면, Pull Request 취소
