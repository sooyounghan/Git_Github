-----
### 작업을 Commit 할 때, 권장사항
-----
1. 하나의 Commit에는 한 단위 작업을 넣도록 할 것
   - 한 작업을 여러 버전에 걸쳐 Commit 하지 않음
   - 역으로, 여러 작업을 한 버전에 Commit 하지않음
  
2. Commit 메세지는 어떤 작업이 이뤄졌는지 알아볼 수 있도록 작성

-----
### Commit Message Convention
-----
1. 널리 사용되는 커밋 메세지 작성 방식
```
type: subject

body (optional)
...
...
...

footer (optional)
```
  - Type
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/496b70a7-7e3f-428e-9ad8-e10ac4ade854">
</div>

  - Subject : 커밋의 작업 내용을 간략히 설명 (일반적으로는 type : subject만 명시)
  - Body : 길게 설명할 필요가 있을 시 작성
  - Footer : Breaking Point가 있을 때 / 특정 이슈에 대한 해결 작업(커밋)일 때 해당 이슈의 번호를 적는 형식
    
2. 예시
```
feat: 압축파일 미리보기 기능 추가

사용자의 편의를 위해 압축을 풀기 전에
다음과 같이 압축파일 미리보기를 할 수 있도록 함
 - 마우스 오른쪽 클릭
 - 윈도우 탐색기 또는 맥 파인더의 미리보기 창

Closes #125
```

3. Gitmoji : https://gitmoji.dev/
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/31f9a43a-108c-4db7-ad8d-b2cce39814db">
</div>
