-----
### OctoTree
-----
<div align="center">
<img src="https://github.com/sooyounghan/Data-Base/assets/34672301/850a6da5-9ac3-4c3c-a480-13290ccc6ad7">
</div>

1. GitHub Repository의 Directory를 보다 편하게 Browsing
2. Chrome Extension에서 설치 가능
3. 설치 링크 : https://chrome.google.com/webstore/detail/octotree-github-code-tree/bkhaagjahfmjljalopjnoealnfndnagc

-----
### GitHub CLI
-----
1. GitHub 작업 전용 CLI 툴
2. 사이트 : https://cli.github.com/
3. 주요 명령어 (https://cli.github.com/manual/)
   - 로그인 / 로그아웃 (명령어 앞에 winpty를 붙이거나 VS Code 터미널에서 실행하면 정상 작동)
```
(winpty) gh (auth (login/logout)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d424bd67-85e8-40aa-bd59-32f36c836218">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/4e377c34-8e39-4a05-9d4a-f7303f9c6baf">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/beb8a9ab-a16b-48a0-90e2-bc652fff915f">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/23fd4d7f-4558-45c3-ad2f-94aefdc817ed">
</div>

  - 레포지토리들 보기
```
gh repo list
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/19c87460-8c84-43d5-8627-ff6c4872c07a">
</div>

  - 프로젝트 클론
```
gh repo clone (사용자명)/(레포지토리명)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/4cdfb08a-75ae-4c74-9810-abe5624fa2f4">
</div>

  - 프로젝트 생성/삭제
```
(winpty) gh repo (create/delete)
ls
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/04e05f69-f13b-4087-9ee9-059038465f6e">
</div>

  - 이슈 목록 보기
```
gh issue list
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c0ba4c73-bb51-438b-af36-d35e3925d561">
</div>

  - 이슈 열람/닫기
```
gh issue (view/close) (이슈 번호)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/f6b86ca3-10f9-475e-aac1-e3a8a7ed4da5">
</div>

  - 이슈 생성
```
gh issue create
```


  - Pull Request 만들기 / 목록 보기
```
gh pr (create/list)
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/6674c7d4-4b7a-45a1-a193-73a04cf5f72f">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/460bcfab-4ca5-4292-b298-546955111fe4">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/052e9bba-9715-44b1-a4c5-f72048409a9b">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/fc08579e-14ea-449e-abfa-02cadef346e7">
</div>

  - Pull Request 보기 / 코멘트 / 닫기 / 병합
```
gh pr (view / comment / close / merge) (PR 번호)
```

