-----
### Global 설정과 Local 설정
-----
1. config를 --global과 함께 지정 : 전역으로 설정
2. 특정 프로젝트에만 user.name / user.email 지정하는 법 : global 키워드를 제거하면 됨
<div align="center">
<img src ="https://github.com/sooyounghan/Web/assets/34672301/5f138032-3b79-4b64-b435-524c903fbc8d">
</div>

-----
### 설정값 확인
-----
1. 현재 모든 설정값 확인
```
git config (--global) --list
```
<div align="center">
<img src ="https://github.com/sooyounghan/Web/assets/34672301/a2ef59e0-e930-402d-a81f-d468c2fbd755">
<img src ="https://github.com/sooyounghan/Web/assets/34672301/dfbdb118-6a1e-4686-b99f-4f37972985d1">
</div>

2. 에디터에서 보기 (기본 : vi)
```
git config (--global) -e
```

3. 기본 에디터 수정 (예시) VS CODE)
```
git config --global core.editor "code --wait"
```
  - 수정이 완료되고 다시 에디터를 보면, 해당 에디터에서 확인 가능
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/14592012-0d76-4984-b1a0-538665dd61b0">
<img src="https://github.com/sooyounghan/Web/assets/34672301/2bc329cf-0051-429d-8a81-a5f288bc92c1">
</div>

  - 또는 code 자리에 원하는 편집 프로그램의 .exe 파일 경로 연결
  - --wait : 에디터에서 수정하는 동안 CLI 중지
  - 이와 같이 설정하면 커밋 메세지 입력창 등도 해당 에디터에서 열리게 됨

-----
### 유용한 설정들
-----
1. 줄바꿈 호환 문제 해결
```
git config --global core.autocrlf (윈도우:true / 맥:input)
```

2. pull의 기본 전략 merge 또는 rebase로 설정
```
git config pull.rebase false
git config pull.rebase true
```

3. 기본 브랜치명 변경
```
git config --global init.defaultBranch main
```

4. 원격으로 push시 로컬과 동일한 브랜치명으로 지정
```
git config --global push.default current
```

5. 단축키 설정
```
git config --global alias.(단축키) "명령어"
```
1. 예시 : git config --global alias.cam "commit -am"
<div align="center">
<img src="https://github.com/sooyounghan/Web/assets/34672301/8b9f1fc9-372c-4de2-8dc0-f873c4982715">
</div>

2. 명령어가 하나 이상이면 작은 따옴표로 묶음 : git config --global alias.unstage 'reset HEAD---'
3. 관련 문서 : https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-Git-Alias




