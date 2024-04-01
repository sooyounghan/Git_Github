-----
### SSH 프로토콜을 통한 인증
-----
1. 공개키 암호화 활용 방식
2. username과 토큰을 사용할 필요 없음
3. 컴퓨터 자체에 키 저장

-----
### SSH 키 등록하기
-----
1. 계정의 Settings - SSH and GPG keys
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/4f46af45-92a4-419a-9d6e-77fa1bc826d1">
<img src="https://github.com/sooyounghan/Web/assets/34672301/db7945c3-a624-4195-af93-ff73a76070eb">
</div>

2. SSH키 존재 여부 확인
   - 터미널 (윈도우의 경우 Bash Shell)에서 ~/.ssh로 이동
```
cd ~/.ssh
```

  - id_rsa.pub, id_ecdsa.pub, id_ed25519.pb 파일 중 하나 존재 여부 확인
```
ls
```

-----
### SSH 키 생성
-----
1. 터미널(윈도우의 경우 Bash Shell)에서 키 생성
```
ssh-keygen -t ed25519 -C "(이메일주소)"
```
  - 원할 시 passpharse 입력
  - 위 과정으로 키 생성 확인
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/560863d8-0a07-4c10-a8d2-e4e1d1dbf6a0">
<img src="https://github.com/sooyounghan/Web/assets/34672301/640b91c5-2f30-442d-af27-b5755b4ff235">
</div>

  + .pub : 공개키 / .pub 없음 : 개인키

2. GitHub에 키 등록
   - 공개키 열람하여 복사
```
cat ~/.ssh/id_ed25519.pub
```
   - New SSH Key를 클릭해 키 이름과 함께 등록
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/fd903519-5340-46bd-9dfb-cf96d71a02a1">
</div>

3. SSH 사용해보기
