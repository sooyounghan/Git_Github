-----
### 다른 Branch에서 파생된 Branch를 옮겨 붙이기
-----
1. rebase --onto 옵션
```
rebase --onto (도착 브랜치) (출발 브랜치) (이동할 브랜치)
```

2. Main branch에서 특정 기능 구현을 위해 branch를 나누어 작업하다가, 보조 기능을 또 branch로 나누어 작업
   - 이후, 특정 구현을 위한 큰 branch 기능을 사용하지 않았지만, 보조 기능의 branch는 사용해야 될 때 해당 기법 사용
     
3. fruit Branch에 파생된 citrus branch를 main branch로 옮겨붙이기
```
git rebase --onto main fruit citrus
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/3d5e7095-f53d-435f-9f03-5cad7fe28446">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c19a325b-16ce-4bff-8316-a7c69638d5aa">
</div>

  - 즉, fruit branch 내 citrus branch가 사라지고, 이 branch가 main branch로 이동 된 것을 볼 수 있음
  - 이제 main branch의 HEAD를 citrus와 일치시켜주면 됨
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8a87b997-f66d-4cbf-a307-49b4329091cb">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1486263a-d4da-4a3f-a64e-ac8c59b7ba16">
</div>

4. rebase --onto를 되돌리기 위한 방법
   - 위의 사항을 진행 후, git reflog를 실행하면 다음과 같음 (rebase --onto 명령 간 여러 내역이 처리됨을 볼 수 있음)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/02628347-f0c9-46bd-b7d6-bb4acd4a4280">
</div>

  - 즉, rebase --onto가 여러 동작을 포함하는 것을 알 수 있음
  - 이 과정에서, 이전 상태로 돌리기 위해서는 reset은 브랜치 별로 이루어지므로, 이 영향을 받은 모든 branch를 하나하나 reset 하거나 혹은 다시 옮겨 붙이는 방법

    + main branch : main은 옮겨붙여진 citrus로 fastforward된 것이 마지막 액션이므로 reflog 기록상에서 그 이전 기록으로 reset --hard를 하면 끝
    + citrus branch
      * 방법 A : citrus branch는 해당 branch가 옮겨지기 전 마지막 커밋인 commit:Lime 부분을 reflog에서 찾아 reset --hard
      * 방법 B : 다시 rebase --onto를 사용해 citrus의 commit을 main으로부터 다시 fruit branch의 orange 부분으로 옮기는 것
        - 이를 위해서는 orange commit으로 checkout 한 다음 새로운 브랜치를 생성 (temp)
        - git rebae --onto temp main cirtus로 cirtus의 두 commit을 해당 위치로 옮긴 뒤 temp branch 삭제
          
