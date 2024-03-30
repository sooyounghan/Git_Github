-----
### Git Tag
-----
1. 특정 시점을 키워드로 저장하고 싳을 때
2. 커밋에 버전 정보를 붙이고자 할 때 (예시) VS Code GitHub)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4c3dd6ba-119b-430d-98f7-6c2e6d8cf331">
</div>

3. Sementic Versioning 정보 : https://semver.org/lang/ko/
   - 즉 Version은 Major.Minor.Patch (예시) 1.0.0)
   - 기존 버전과 호환되지 않게 API가 바뀌면(큰 변화 발생) 'Major'
   - 기존 버전과 호환되면서 새로운 기능 추가 'Minor'
   - 기존 버전과 호환되면서 버그를 수정한 것 'Patch'
  
-----
### Git Tag 달아보기
-----
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2ea9d70d-1cf9-40d4-8d02-1e980d960d1a">
</div>

1. 특정 커밋을 지정하지 않으면, 마지막 커밋에 태그 달기 (lighweight)
   - Source Tree의 경우, 태그 메뉴에서 설정 가능
```
git tag v2.0.0
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/c7de17f5-abf9-4796-88f9-935281f04804">
<img src="https://github.com/sooyounghan/Web/assets/34672301/77b9432e-329b-4d62-905d-0560c9534552">
</div>

2. 현존하는 태그 확인
```
git tag
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e09ee826-7fd3-425b-ae4f-da39a6bc9561">
</div>


3. 원하는 태그 내용 확인
```
git show v2.0.0
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1793e112-c42b-4b60-b56b-e08499fc05dc">
</div>

4. 태그 삭제
```
git tag -d v2.0.0
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/32cf681d-e351-4095-8456-bfa5700f0e44">
</div>

-----
### Git Tag 달아보기 (Annotated)
-----
1. 마지막 커밋에 태그 달기
```
git tag -a v2.0.0
```
  - 입력 후 메세지 작성 가능도 하며, 아래와 같이 작성 가능
```
git tag v2.0.0 -m '자진모리 버전'
```
  - -m 태그가 -a 태그를 암시


2. 태그 확인
```
git show v2.0.0
```

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/bcea8976-92f5-48ab-82d8-884b01dae525">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2c5d2753-b849-48c6-9a35-e088245a4b40">
</div>

-----
### 원하는 Commit에 Tag 달기
-----
```
git tag (태그명) (커밋 해시) -m (메세지)
```
< 예시 >
1. v1.0.0 (굿거리 버전)
2. v1.2.1 (휘모리 버전)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/b02381b9-6074-4877-9b07-73552ac85dae">
</div>

  - 위의 태그 포함 총 3개의 태그 존재

-----
### Tag Filtering
-----
```
git tag -l '필터링'
```
< 예시 >
1. 버전이 1인 모든 태그를 보고 싶다면? (v1.*)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/7a121c8b-1259-4d69-9dba-ffe2c015aafb">
</div>

2. 버전이 0으로 끝나는 태그를 보고 싶다면? (*.0)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/238d14c6-34b2-4b82-8aff-c2efb1b82011">
</div>

-----
### 원하는 버전으로 Checkout
-----
```
git checkout 태그명
```
1. 예를 들어, v1.2.1버전으로 checkout하고 싶다면? (즉, 해당 태그를 가진 곳으로 익명의 branch를 생성해 이동)
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/baa10026-8586-4bbd-9e0d-2f480f0178be">
</div>

2. switch로 이전 branch로 이동 가능
   
-----
### 원격의 태그 동기화
-----
1. 특정 태그 원격에 올리기
```
git push (원격명) (태그명)
```
   - local의 v2.0.0 태그를 원격으로 올리기
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d1182a70-8b96-4c68-97b6-97d3229f5a87">
</div>

   
2. 특정 태그 원격에서 삭제
```
git push --delete (원격명) (태그명)
```
   - 올렸던 v2.0.0 태그 삭제
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/e21a6705-1a9c-4fdc-b3f4-12bf197faf7a">
<img src="https://github.com/sooyounghan/Web/assets/34672301/d3d840b0-2785-461b-982e-a73ecdd08104">
</div>

3. 로컬의 모든 태그 원격으로 올리기
```
git push --tags
```
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/36e6488f-bcc6-44c9-b5df-1f42f79502bf">
<img src="https://github.com/sooyounghan/Web/assets/34672301/1786a86f-ca91-4e78-8d31-bb727c6de93a">
</div> 

-----
### GitHub의 Release
-----
1. Tag 중의 원하는 부분을 Release 가능
2. 회원 뿐 아니라 방문자들이 다운받을 수 있도록 제공하는 방법

<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/66a48460-78ea-43bf-bc64-ea12bf4406b2">
<img src="https://github.com/sooyounghan/Web/assets/34672301/65d425bb-8d22-4cff-93c4-3151ce3f37b8">
<img src="https://github.com/sooyounghan/Web/assets/34672301/f202a12e-5d6c-448f-9c06-a78851b44acf">

</div> 
