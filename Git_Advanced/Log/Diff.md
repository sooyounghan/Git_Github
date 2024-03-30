----
### git diff
----
1. Working Directroy의 변경 사항 확인
```
git diff
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ba2fbdab-6c47-4a6e-a94c-074626edb69e">
</div>

2. 파일명만 확인
```
git diff --name-only
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c6fa222f-9e7e-475c-831a-e6bf7036497f">
</div>

3. Staging Area 확인
```
git diff --staged
git diff --cached
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/a845a311-acc1-45d8-98d7-48cca74f558a">
<img src="https://github.com/sooyounghan/Web/assets/34672301/0d5570e7-7980-4f56-848c-1e6f124ac8e4">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c51ce085-6874-4d03-8271-c6b0a9675eda">
</div>

4. Commit 간 차이 확인
```
git diff (Commit1) (Commit2)
```
  - Commit Hash 또는 HEAD 번호로 출력
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2c0e35dd-a08d-4092-a7b5-b7aac5238a61">
<img src="https://github.com/sooyounghan/Web/assets/34672301/91f1389e-bb76-41cc-89ae-a9751a37faea">
</div>

  - --name-only만으로 파일명만 비교 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/40853db4-1baa-4e00-ad30-8077e9ced9b1">
</div>

  - 현재 커밋과 비교하려면 이전 커밋만 명시

5. Branch 간 차이 확인
```
git diff (branch1) (branch2)
````
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/44119060-17e0-4d78-b302-2a1206779fac">
<img src="https://github.com/sooyounghan/Web/assets/34672301/64cd114a-3caf-41e1-9811-93108a35dcda">
</div>
