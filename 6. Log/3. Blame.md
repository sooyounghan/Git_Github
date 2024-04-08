-----
### git blame
-----
1. 각 라인의 작성자를 확인
2. 파일의 부분별 작성자 확인하기
```
git blame (파일명)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b7c11166-e3d4-4ba6-978d-c920c4f3a09a">
</div>

  - Commit한 사람의 local/global name이 출력

3. 특정 부분 지정해서 작성자 확인하기
```
git blame -L (시작줄) (끝줄, 또는 +줄수) (파일명)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/545be79c-d08e-4e6c-9b1f-f8809c47bb9d">
</div>

  - 10,12 : 10 ~ 12 번째 Line을 의미
  - 10,+3 : 10번째를 포함하여 총 3개의 Line, 즉 12번째 Line 의미

4. VS Code의 GitLens 확장 방법
