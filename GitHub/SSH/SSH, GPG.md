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

-----
### GPG 키를 통한 검증
-----
1. GitHub 커밋 내역 살펴보기
   - Local에서 Push한 Commit과 GitHub에서 작성한 커밋 비교
   - Verified : 신뢰할만한 출처에서 커밋되었다는 인증 (즉, GitHub에서 Commit 한 것과 동일)

2. GPG 툴 설치
   - https://www.gnupg.org/download/
   - gpg --version으로 확인

3. GPG 키 생성
   - https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key
  
4. New GPG Key를 클릭해 등록
   - https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key
  
5. 사인하기
   - Commit에 사인 : 명령어에 -s 옵션 추가
```
git commit -S -m '(메시지)'
```

   - Tag에 사인 : 명령어에 -s 옵션 추가
```
git tag -s (태그명) (커밋 해시) -m (메시지)
```
