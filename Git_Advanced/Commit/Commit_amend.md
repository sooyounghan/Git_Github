-----
### git commit --amend
-----
1. 마지막 커밋 수정하기
2. 커밋 메세지 변경
   - Panthers의 members에 Hoki 추가하고 Commit (커밋 메시지: 횻홍)
   - 커밋 메세지 변경 : Add a member to Panthers

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/6ae607ac-4386-4d9f-9c2a-718026f5c44c">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b0cadf58-6dee-46c6-8a68-a60422120921">
</div>

-----
### Commit에 변화 추가
-----
1. 마지막으로 Commit한 부분에 놓친 Commit 부분이 있을 때, 이 작업 하나를 마지막 Commit에 적용하고 싶을 때 사용
2. 1번에서 git add .를 한 후, git commit --amend 이용
3. 즉, 다른 Commit을 하려고 할 때, git commit --amend로 마지막 커밋에 포함

4. Pumas의 members에 Poki 추가하고 Staging 영역에 올린 후, git commit --amend를 이용해 마지막 커밋에 같이 포함
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/22cdcba7-f891-4205-9f62-c07511ca21f3">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0a74cf44-0b98-4569-a25c-c7dc91a3d1d7">
</div>

5. git commit -a --amend -m "메세지명" : add까지 자동으로 한 후, commit하되, 가장 마지막 commit 수정
   
-----
### Commit 메세지 한 줄로 변경
-----
```
git commit --amend -m '메세지명'
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a3384060-0ad6-4f25-af9e-dfcfe936af34">
</div>


`
