-----
### GitHub Actions를 사용한 자동화
-----
1. CI/CD : 지속적 통합과 배포 (자동화와 관련)
   - 참고자료 :  https://www.youtube.com/watch?v=UbI0Q_9epDM 
   - Continuous Intergration (지속적 통합)
   - Continuous Deployment/Deliveery (지속적 배포)
   - 서로 다른 개념이지만, 보통 함께 구축되므로 CI/CD라고 부름
   - 즉, 프로그래머들이 소프트웨어를 코딩하고나서 이를 최종 배포까지 하는 과정에서 진행되는 일 (= 자동화)
   - 동종 : GitLab CI/CD, BitBucket Pipelines
   - 참고 자료 : https://www.yalco.kr/43_ci_cd/

2. Continuous Intergration (지속적 통합)
   - Git과 같은 버전 컨트롤 시스템을 통해 각자가 작업한 코드들을 출시할 결과물로 통합
   - 여러 사람이 작업함으로 발생할 수 있는 문제(에러, 코드 충돌 등)들을 방지하려면 이러한 통합 작업을 수시, 즉 지속적으로 하게 해야하는데, 이런 테스트 과정을 매번 거치기에는 번거로움
   - 이를 자동화할 필요가 존재, 즉 이런 CI의 자동화를 구현해주는 다양한 도구와 서비스 존재

3. Continuous Deployment/Deliveery (지속적 배포)
   - 소프트웨어를 코딩한 결과를 최종 사용자에게 넘겨주는, 실행가능하도록 하는 단계를 의미
   - 즉, 코딩을 마칠 때 마다 지속적으로 배포
   - 따라서, CI가 성공적으로 이뤄지고나면, CD가 진행되는 것
     
-----
### 설치형 자동화 도구 - Jenkins
-----
1. 가장 대표적 도구
2. 대표적인 설치형 CI/CD 자동화 툴 젠킨스의 화면
3. 젠킨스를 실행하면, 브라우저에서 다음과 같은 콘솔 화면 볼 수 있으며, 새로 자동화 작업을 작성하는 화면
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/39fbf1b9-8c0e-4d5f-8d39-f8f71d48a48a">
</div>

4. Gradle을 사용해 빌드 명령어를 내릴 것인지 지정하는 화면
   - 이후 하단의 Post-Build Actions에서 빌드 이후 실행될 작업, 이를 테면 Slack 메세지 보내기 등 설정 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/66333aa7-82f2-475e-bd06-40348c42b88c">
</div>

5. CI/CD가 진행되는 모습 또는 진행된 내역 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/4868a14e-a7f2-43c8-b06d-5b16fc43dda2">
</div>

-----
### 클라우드형 서비스 자동화 도구 - Travis CI
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/559fbbf3-b377-422d-a8f7-b9dca1c50058">
</div>

   - Travis CI에서 자동 테스트가 이루어진 내역들을 보여주는 화면
   - 테스트에서 오류가 발생했음을 나타내는 메세지들과 함께 상세 내역 볼 수 있는 로그 존재
   - .travis.yml 예시
```
# 사용할 언어와 버전
language: node_js
node_js: 
  - "14.15"

# 작업 전 수행할 것
before_install:
  - npm update

# travis 브랜치에서만 수행
branches:
  only:
    - travis

# 테스트(또는 추가 작업) 후 결과 전송
notifications:
  email:
    recipients:
      - yalco@kakao.com
```

      + Travis에서 지정한 형식으로, 자동화 작업들을 세팅한 ㅁ누서
      + 이 파일을 프로젝트 최상위 폴더에 넣어, push 등 이벤트가 발생할 때마다 위 작업들이 실행되도록 함
      + 대다수 클라우드형 / Git 저장소형 서비스들이 비슷한 방식으로 CI/CD 작업들을 설계

-----
### GitHub Actions
-----
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/26fac4ae-b7dd-4297-b818-0b65931103e0">
</div>

1. GitHub의 Actions 탭에서 자동화할 작업들을 작성하는 화면
2. 왼쪽에는 yml 파일로 작업들을 직접 작성하는 에디터 존재
3. 오른쪽에는 이미 작성된 탬플릿을 가져올 수 있는 마켓플레이스 존재
4. 소스를 Push하는 등 지정된 이벤트가 발생하면, GitHub에서 제공하는 클라우드 컨테이너 공간에서 빌드나 테스트, 슬랙 메세지 등의 작업, 배포 등이 진행
   
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/dfa76a0e-cac6-4027-af9a-c9e90fc718e9">
</div>

5. GitLab CI/CD 진입 화면으로, 프로젝트에 따라 템플릿 선택 가능

-----
### GitHub Actions 살펴보기
-----
1. github.io 페이지의 액션 (자동화로 인해 Action)
   - 해당 레파지토리 페이지에서 Actions Tab 살펴보기
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/5de730c3-01c9-46d7-8576-974c5999fbc1">
</div>

   - 새로운 Commit Push 직후 다시 살펴보기
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/6ca08797-42c7-457a-a99f-78f493a946d1">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/110ec4c6-b285-4338-896a-ef455fce2952">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/327743a5-f0bb-483a-892e-bc4fddd09439">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/80408e11-c534-4e59-bc69-df048f247e3a">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/3bc32a53-f85d-4998-a376-5631eabe756f">
</div>

2. 다른 프로젝트에서 Action 추가해보기
   - Actions 탭에서 액션들 살펴보고 적용해보기
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/15037a60-5446-4073-ae98-4313bec4e9c8">
</div>

   - MarketPlace 살펴보고 적용해보기
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/9066f5e3-a537-4077-bd15-6813d398450b">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c5a3229b-7120-463a-8cc6-fcf3a11c2267">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/661ba1c6-8113-4958-a75b-f5088f863743">
</div>

   - Simple Workflow
```
# This is a basic workflow to help you get started with Actions

name: CI

# Controls when the workflow will run
on: // 어떤 것에 반응 할 것 인지?
  # Triggers the workflow on push or pull request events but only for the "main" branch
  push: // push 할 떄
    branches: [ "main" ] // main branch 일 때,
  pull_request: // pull_request 할 때
    branches: [ "main" ] // main branch 일 때,

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs: // 어떤 것이 실행 될 지?
  # This workflow contains a single job called "build"
  build: // Code를 실행하기 위해
    # The type of runner that the job will run on
    runs-on: ubuntu-latest // 우분투 최신버전에서 실행

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it // 실행 작업
      - uses: actions/checkout@v3

      # Runs a single command using the runners shell // 실행 작업
      - name: Run a one-line script
        run: echo Hello, world! // 작업

      # Runs a set of commands using the runners shell // 실행 작업
      - name: Run a multi-line script
        run: | // 작업
          echo Add other actions to build,
          echo test, and deploy your project.
```
   - Start Commit - Commit New File로 새로운 폴더(.github\workflow) 및 파일(예시로 위의 파일이면, 위 파일) 생성
   - Commit 후 Pull하면, Local로 저장

-----
### 자동화 과정 예시
-----
   - 예시 파일 : test.js
```js
const evenNumber = 10

if (evenNumber % 2 !== 0) {
  throw '오류'
}

```

   - action을 위한 파일 : test.yml
```
name: Node.js CI

on:
  pull_request:
    branches: [ main ] // main branch의 pull_request가 들어오면 Action

jobs:
  build:

    runs-on: ubuntu-latest // builde는 우분투 가상 공간에서 작업 수행

    strategy:
      matrix:
        node-version: [12.x, 14.x, 16.x] // Node.js의 세 버전에서 실행

    steps:
    - uses: actions/checkout@v2

    - name: Execute text // Action 마다 이름 지정 가능
      run: npm test // 테스트 실행

    - name: if fail
      uses: actions/github-script@0.2.0
      with:
        github-token: ${{github.token}}
        script: |
          const ref = "${{github.ref}}"
          const pull_number = Number(ref.split("/")[2])
          await github.pulls.createReview({ // PR에 Review 작성
            ...context.repo,
            pull_number,
            body:"테스트가 실패했습니다.",
            event: "REQUEST_CHANGES"
          })
          await github.pulls.update({
            ...context.repo,
            pull_number,
            state: "closed" // PR을 자동 Close
          })
      if: failure()       // 만약 실패하면,           
```
   - 즉, 이 자동화 파일은 Pull Request 과정일 때, GitHub에서 test.js의 테스트를 진행해 오류가 발생하면, 자동적으로 PR 취소
   
   - 다른 Branch에서 작업을 한 다음, 원격의 Main에 Pull Ruest 요청
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/249fa255-be41-424a-b26b-8fb6d268b65b">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/34d875ea-ac94-453d-b648-aeac15c5ab15">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/5f9f7926-34f2-42e6-aa8e-36cdb2dce291">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/9b991326-fe23-4bab-9d9a-2be444f455a4">
</div>


   - Test를 진행해 실패하면, Pull Request 취소
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/7ae34e8f-6cc0-4b0a-ae49-1f49dd6b7d76">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/25271b4a-016e-4f93-890d-8bd131c06733">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/305c5d76-7959-46b1-abd4-0746e4bcebe4">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/965f2ff4-ae9f-4323-8ff0-f71ebba4ca78">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/b1ae4b40-bb42-41e3-ad83-8ab274209418">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/95f0a383-63ce-4937-9af3-b87adf36cf82">
</div>

   - 이런식으로, 오류가 나는 PR은 자동 취소
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/8c4dd9b8-81a7-4ab5-b186-673c733360f8">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/827a78c0-55af-4f00-ac3b-51aac35985f0">
</div>

   - 제대로 실행한다면 ?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/707b8ed1-e3c2-41a0-ad14-35b7a8aa594e">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/51e3c8f5-f1fc-458c-9b85-af8538589469">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/b97f0a04-d16d-4a94-898b-73d25c4bd606">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/e8f1c4b5-b3e4-4eea-a6a3-5a4b601b9cae">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/0165c850-78a8-4499-8606-9551ef0e40c5">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/2136e086-0ca7-4af6-95f1-7b851aa78f33">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/e2cf57a3-6058-49aa-ae50-5c5e6f0ba0b7">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/61eda727-8bde-49bb-9c6f-be4cd0a3b71d">
</div>
