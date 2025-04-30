-----
### git bisect
-----
<현재 상태>
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/83fd8c1f-5fa9-4d2c-9a20-891d9dc8b9da">
</div>

1. 이진 탐색 알고리즘으로 문제 발생 시점을 찾아냄

2. 예제
   - error : false (에러 없음) / error : true (에러 발생)
   - v3 시점이 의심되는 상황
   - 이진 탐색 시작
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2aa4339a-d685-43d0-af5d-d9a8d93ac2a8"></div>
   
```
git bisect strat
```
   - v20은 현재 error : true (bad)
   - 오류발생 지점임을 표시
```
git bisect bad
```

<div align="cetner">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d103f461-d10d-490b-97ed-8bcec658d252">
</div>

  - 의심 지점으로 이동 (v3)
```
git checkout (해당 Commit Hash)
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/85b084b8-bc6e-4cd8-829c-5ab478da9670">
</div>

  - 에러 미발생
  - 오류가 발생하지 않을 시 양호함 표시 (good)
```
git bisect good
```
<div align="cetner">
<img src="https://github.com/sooyounghan/Web/assets/34672301/63d3d6a9-e21c-4559-8fa0-0cf718d1c26f">
</div>

  - 따라서, 이제 중간 지점인 v11로 이동해 bisect 시작
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4d7164be-5034-4b04-b853-60f32094cde6">
</div>

  - error : true 로 bad 표시 후, 다음 v7으로 이동하나 error : true

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/be822acf-cd44-47e3-b12d-48139cfba54d">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9457d3af-dd7b-46cb-93aa-040d3e3fad64">
</div>

  - 다음 v5 이동하나 아직 error : true로 역시 bad
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/09265f8d-52a6-4eb0-96bf-45c91b5d90ea">
<img src="https://github.com/sooyounghan/Web/assets/34672301/9aa06377-213f-40c7-80a1-e04fbc965821">
</div>

  - v4로 이동하였고, error : false 확인 (error가 v5인 것 확인) (good)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d22cd930-7e94-4cca-9043-ada1c125c764">
<img src="https://github.com/sooyounghan/Web/assets/34672301/5005da55-5ae6-40b0-b4b0-aa9216430462">
</div>

  - 오류를 찾을 때 까지 반복
```
git bisect good/bad
```

  - 이진 탐색 종료
```
git bisect reset
```

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8471bf76-83be-4596-a005-18fee4308bb1">
</div>
