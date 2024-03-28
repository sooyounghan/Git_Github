-----
### branch 
-----
1. branch는 항상 main branch에서 진행되며, 그 외 branch는 이 branch에서 나눠져서 작업 수행하는 것을 생각
2. 그렇다면, 이들을 모두 main branch로 가져오는 방법은?

-----
### branch 병합 방식 : Merge vs Rebase
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/ae543569-04f5-4577-9de3-66deec8673f4">
</div>


1. merge : '병합'이라는 말처럼, 두 개의 branch를 묶는 것
   - 즉, 원래 branch와 조합될 branch가 서로 합쳐지는 것
   - 즉, main branch와 작업했던 분기 branch의 변화들을 한 번에 적용
   - 좀 더 심화된 내용은 추후에 다루기로!

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/45b1aba0-7485-4b98-8a6d-0c6c79ca8862">
</div>
2. rebase : branch 마디, 즉 commit들을 적용하고자 하는 대상 branch로 옮기는 것
   - 마치 main branch에 분기된 branch의 commit들을 하나하나 추가한 것 처럼 되는 효과
  
3. 둘의 차이점은?
   - 히스토리, 내역의 차이
   - rebase의 history는 깔끔하게 한 줄로 정리가 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/45b1aba0-7485-4b98-8a6d-0c6c79ca8862">
</div>

   - merge는 branch의 흔적을 남김 (많은 프로젝트를 진행하는 곳에서는 꽤 복잡하게 느껴질 수 있음)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b7e526ea-a8eb-40ef-b392-8469d386e4f5">
</div>

  - 즉, merge는 branch 기록을 냅두고 마지막에서 병합하는 개념 (branch의 사용 기록을 남기는 목적)
  - rebase는 branch에 대해 main branch로 이동하여 깔끔하게 보이는 것 (history를 깔끔하게 정리하기 위한 목적)

* 참고 : 협업하는 프로젝트 간에는 rebase 사용은 좋지 않음 (같이 협업하는 과정에서 혼동의 여지가 발생 가능성이 있음)
