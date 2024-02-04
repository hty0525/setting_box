### GIT 명령어

```
git init
// 깃 사용 명령어
```

```
git config --global user.name “Your name”
git config --global user.email “Your email address”
//전역 깃 계정 설정
```

```
git config user.name “Your name”
git config user.email “Your email address”
//해당 레포의 깃 계정 설정
```

```
git config --global --list
// 깃 전역 설정 조회
```

```
git config --list
// 저장소별 설정 정보 조회
```

```
git clone {저장소 url}
//원격 저장소 클론
```

```
git remote add <원격 저장소> <저장소 url>
```

```
git remote -v
//현재 연결된 원격 저장소 보기
```

```
git remote add {원격 저장소} {저장소 url}
git remote add origin https://github.com/hty0525/setting_box.git
//원격 저장소 추가 주로 원격 저장소 origin으로 표현되는듯,,?
```

```
git remote remove {원격 저장소}
git remote remove origin
//기존에 연결된 원격 저장소 삭제
```

```
git add .
// 현재 변경된 파일들 전체를 스테이징에 추가

git add component
git add page/Main.tsx
git add {폴더 혹은 파일}
// 해당하는 폴더만 추가
```

```
git commit -m "커밋 메세지"
//추가된 저장사항의 커밋메세지

git commit -m "커밋 메세지" -m "커밋 설명"
// 커밋 메세지 + 설명
```

```
git push
//저장된 내용 지정된 원격 저장소에 올리기

git push -f
강제로 푸쉬가 필요할때 사용 가급적 사용 지양권장
```

```

```

참고 <a href="https://medium.com/@joongwon/git-git-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC-c25b421ecdbd" target="_blank">링크</a>
