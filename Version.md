-----
### 추적하지 않는(Untracked)
-----
1. .gitignore에 practice1.jsp 파일을 추가한 결과, 다음과 같이 변경되었고, 추가적으로 다시 한 번 git status를 보면,
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/68694714-50ff-4cf8-8a69-204b638ef93a">
</div>

2. Untracked File : git의 관리에 들어간 적이 없는 파일

-----
### git add
-----
* git add의 예시를 위해 현재 /git_practice Directory에 test.txt를 생성
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/e285f738-b5c8-4ffa-9cf7-f1c39ada2f52">
</div>

1. 프로젝트에서 일어난 일종의 '변화'를 알리는 것
2. 예시 (하나의 파일에만 적용 /git_practice/test.text 파일에 적용)
```
git add test.txt
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/1da5f2bb-bd55-408a-9fc7-30eee9adff3f">
</div>

3. 다시 한 번, git status로 확인하면
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/6d3aa5a5-6856-4bae-8230-5219a7f02cbd">
</div>

  - Changes to be committ : Staging Area으로 이동하여 Commit 준비가 되었음을 알려줌
  - Untracked files : 아직 git의 관리에 들어가지 않은 파일들

4. 예시 (모든 파일 적용 /git_practice/* 파일에 적용)
```
git add .
```
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/bcdf3a8e-4c5d-4830-bd29-3cb3dce3b2b3">
</div>

<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/fe3d495b-34c3-4c54-8881-358415e5485b">
</div>

  - 이처럼, commit 준비가 되었음을 알 수 있음

-----
### git commit
-----
1. 새로운 버전을 만든다는 의미
```
git commit
```
2. git commit을 실행하면, Vim 모드로 진입
  - vi(vim) 단축키
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/01c2acff-54c7-4bd4-9938-a3fb790a40a1">
</div>

  - 필수 단축키
    + 입력 시작 : i
    + 입력 종료 : esc
    + 저장 없이 종료(입력한 것이 없을 시) : :q
    + 저장 없이 강제 종료 : :q!
    + 저장하고 종료 : :wq

  - vim 모드에서 "first commit"이라고 입력하고 저장하고 종료(:wq)하면, (통상적인 의미로 first commit은 어떤 프로젝트의 첫 버전이 만들어질 때 사용)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/133a559b-e072-44d8-9233-6ec26b8560b0">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/c7f774cb-b5da-4a70-9096-65d0107f7e4f">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/82bb929a-d5ed-49bd-8c8c-1f2c566d9bf4">
</div>

  - 이처럼 commit 됨을 알 수 있음
  - 이 상태에서, git status로 확인하면,

<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/dd309c08-f498-4e9e-80b7-af8f9d33f869">
</div>

   - nothing to commit 상태로 변경 / 현재 상태를 Source Tree에서 접근하면 ?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/3d7f92d0-942f-4acf-8840-ace16fa19a38">
</div>

   - 다음과 같이 commit 된 것을 확인 가능

   - git bash에서는 git log로 명령어로 확인 가능 (모든 Commit은 고유의 문자열 일련번호를 가지고 있다고 생각하는 것이 좋음)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/71520a27-b95c-48ab-a526-5b0c50b82ec1">
</div>

3. 커밋 메세지와 함께 저장
```
git commit -m "first commit"
```

-----
### 변경사항 발생에 따른 버전 설정
-----
1. test.txt 파일을 삭제히고, practice2.jsp의 내용을 일부 변경하고, practice3.jsp를 하나 생성한다고 하자.
2. 다음과 같이 변경됨을 알 수 있음
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/5e90a2fc-755c-4aae-a9ca-39c17e23e92e">
</div>

3. 이 상태에서 git status로 확인하면,
<div align="center">
<img src ="https://github.com/sooyounghan/Git-Github/assets/34672301/b2417011-303a-4627-ac90-7fdf151fa340">
</div>

  - delete / modified / untracked file의 정보를 알 수 있음


4. git diff : 변경사항을 좀 더 구체적으로 내용을 보여주는 명령어
```
git diff
```
<div align="center">
<img src ="https://github.com/sooyounghan/Git-Github/assets/34672301/42b9cfd6-5120-4349-bd00-20e56c197812">
</div>

    j : 아래로 스크롤
    k : 위로 스크롤
    :q : 닫기

5. 다시 한 번, git add .로 commit 준비를 하면,
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/785b3101-606d-4f74-b0ce-6b85aa600205">
</div>

  - 변경된 사실에 대해 모두 저장 준비가 완료됨을 알 수 있음

6. git commit -m 명령어를 통해, commit을 실시하고 status를 보면,
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/65b945fa-1f53-433d-865c-f367ab50e582">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/d8cc148c-1cce-4708-9ae5-7aebcff1eaf3">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/373e618e-e079-4c19-a1c5-bc119ade2057">
</div>

  - commit이 된 것을 확인 가능(git bash, source tree)


-----
### add + commit
-----
```
commit -am "메세지"
```
1. 단, 새로 추가된(Untracked) 파일이 없을 때 한정
2. 즉, 새로 추가할 파일이 있다면, 해당 명령어는 사용하지 못함


-----
### 커밋 진행
-----
1. practice3.jsp 파일 일부 변경 (Commit Message : Modified practice3.jsp)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/bcb80044-6594-4444-9191-3c31324abd15">
</div>

2. practice4.jsp 파일 생성 (Commit Message : Add practice4.jsp)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/2291bf35-0cc1-454e-b89e-51aacc10420f">
</div>
 
3. practice3.jsp 삭제, practice4.jsp 파일 수정, practice5.jsp 생성 (Coomit : Delete Practice3.jsp, Modified practice4.jsp, Create practice 5.jsp)
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/e56d1ae1-7c0e-4382-9fc3-d99966ee1266">
</div>

4. 이에 따른 source tree 변화
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/f189e20d-2a4a-4df6-8e28-dc5ab7c02b83">
</div>

5. 결과 : 현재 해당 main에는 총 5개의 버전이 있는 것으로 생각하는 것이 편함

-----
### Reset vs Revert
-----
1. reset
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/616c94c8-0fa8-4d0f-8460-712fc3013756">
</div>

   - 과거 시점으로 되돌리는 것 (원하는 시점으로 돌아간 뒤 이후 내역 삭제)
   - 과거 시점으로 돌아감에 따라, 이후 행적은 history에서 삭제
  
2. revert
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/42265f79-1d8f-46de-8dd0-ee8358d860ac">
</div>

   - 내역을 삭제하는 것이 아니라 변화를 반대로 수행하는 것을 하나 추가하는 것 (되돌리기 원하는 시점의 커밋을 거꾸로 실행)
   - 즉, 추가한 게 있으면 삭제하고, 변경한게 있다면 변경되지 않도록 설정
   - 결과적으로는 과거 시점으로 돌아간 것과 같은 효과
   - 이러한 변화의 기록이 필요할 때 사용하면 유용
     
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/1fcce867-5cfb-4e45-ae35-cfadea2683b5">
</div>

   - 또는, 기존 내역은 유지하되, 과거 일부 특정 시점에 대한 변경이 필요할 경우 사용

 3. 개발 과정에서 reset을 하면 이를 기반으로 작업한 다른 사람들의 코드와 심각한 충돌 발생
 4. 때문에, 한 번 공유가 된 커밋들은 revert를 통해 되돌리는 것이 좋음

-----
### Reset
-----
1. git log로 현재 커밋 내역 확인
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/baf25367-45d8-483f-a2a8-13da4d09db74">
</div>

2. 형식
```
git reset --hard (돌아갈 커밋 해시값)
```
 - 돌아가려는 시점의 해시값이 필요

3. 첫 번째 커밋 상태로 돌아간다면, 다음과 같이 설정 후 git log 확인
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/fa18829f-7294-455a-902f-a3f7e84fb084">
</div>

4. Source Tree 및 변화
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/beb82743-c75e-428f-bd61-99f2de649a08">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/7e887210-b63d-47ce-8f39-5c562683ab1f">
</div>

5. 이 상태에서 현재까지 진행한 .git을 지우고, 백업해 둔 .git 폴더를 다시 사용하면 ?
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/de6563e9-bddf-41a5-9fc1-36ef30dc2291">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/f1067d40-008e-47c0-b419-99235ac5c728">
</div>

  - 원래대로 돌아온 것으로 git은 판단
  - git status 확인 결과

<div align="center">
<img src = "https://github.com/sooyounghan/Git-Github/assets/34672301/f8e6150c-9866-4043-9bee-730406d693c0">
</div>

6. 그렇다면, 현 커밋 상태를 다시 초기화한다면?
   - 즉, 현재 git의 커밋 상태는 첫 번째 커밋 상태였음
   - 백업해둔 파일에 의해 다시 기존 파일 구조로 되었으므로 git의 입장에서는 첫번째 커밋의 기준의 입장에서 git 파일들이 관리가 됨
     
   - 이 상태에서 현 커밋 상태로 초기화를 하면,
```
git reset --hard
```
  - 돌아갈 커밋 해시값을 붙이지 않으면, 마지막으로 선언한 커밋으로 이동 (즉, 백업한 파일의 마지막 커밋이었던 부분으로 이동)
  - 이 과정에서, test.txt는 두 간극 차이에서 마지막 커밋으로 기준으로 봤을 때, 자신이 관리한 파일이 아니므로 관리하지 않음
  - test.txt를 삭제하고 접근하면,
<div align="center">
<img src = "https://github.com/sooyounghan/Git-Github/assets/34672301/e6aac546-fea3-420e-a231-207781e50b36">
<img src = "https://github.com/sooyounghan/Git-Github/assets/34672301/d2ddd121-1da1-436e-aeb3-112ccb5cf5b8">
</div>

  - 다음과 같이 5번째 커밋 상태로 되돌아오게 됨 (source tree 참고)
<div align="center">
<img src = "https://github.com/sooyounghan/Git-Github/assets/34672301/a68a3917-a247-4aba-b3be-2a07014c8708">
</div>

-----
### Revert
-----
1. reset : 과거 시점으로 돌아갈 hash값
2. revert : 과거 시점으로 되돌릴, 취소할 hash값을 구함
```
git revert (되돌릴 커밋 해시)
```

3. Deltet practice3.jsp, Modified practice4.jsp, Create practice5.jsp으로 revert한다고 하면, 이 때의 해시값은
<div align="center">
<img src ="https://github.com/sooyounghan/Git-Github/assets/34672301/2c12a893-8565-41cd-a142-46ec199b9832">
</div>

4. git revert로 진입하면, vim 상태로 진입
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/02240bb3-8ac3-4f4f-9ad9-d56084df5f3d">
</div>

 5. 해당 기점으로 revert 완료
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/02240bb3-8ac3-4f4f-9ad9-d56084df5f3d">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/fce864d3-f73e-4d21-84c5-276f9f2c19e6">
</div>

6. Source Tree에서 보면, 해당 커밋에 대해 반대로 실행한 커밋 한 개가 더 존재 파악 가능
<div align="center">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/71a280c2-f978-432b-bf3b-2e3c83dcb2aa">
<img src="https://github.com/sooyounghan/Git-Github/assets/34672301/55b3f315-2bd3-45e0-8d3e-c6dc2db43307">
</div>

   - 즉, 마지막 커밋과 이 커밋 사이에 있는 커밋들을 건너뛰고, revert로 지정한 커밋에 대한 변화만 가져옴
   - 또한, 내역을 삭제하면 reset은 그 내역이 사라지지만, revert는 무엇을 취소했는지 또 history에 기록에 남게되므로 주로 사용
