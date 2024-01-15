# 📍 Git 기본 명령어 / 문법 정리

<br>

### ✅ 초기 설정
: git 설치 후 한번만 실행
```bash
git config --global user.email <이메일>
git config --global user.name <이름>
```

<br>

### ✅ Git 저장소 생성
#### ✔️ init
- `git init` : `.git directory`를 생성해주는 명령어
- 관리하고 싶은 최상위 위치에서 실행
#### ✔️ .gitignore생성 
- git으로 관리하지 않을 파일 설정
- [gitignore.io](https://www.toptal.com/developers/gitignore) 사이트에서 생성가능

<br>

### ✅ Git 상태 체크
#### ✔️ status
- `git status` : 현재 git으로 관리되고 있는 파일/폴더의 상태를 출력
#### ✔️ log
- `git log` : commit내역 확인
#### ✔️ reset
- `git reset HEAD^` : 마지막 commit 취소

<br>

### ✅ Branch (브랜치)
: master server를 이루기 위한 기능별 server (충돌방지)
- `git branch -all` : 모든 브랜치 조회
- `git branch <브랜치이름>` : 브랜치 생성
- `git switch <브랜치이름>` : 브랜치 이동

<br>

### ✅ 코드 수정하고 저장소에 저장하기
#### ✔️ add
- `git add <파일/폴더이름>` : working directory에서 staging area로 추가
- `git add <.>` : 모든 파일, 폴더를 staging area로 추가
#### ✔️ commit
- `git commit -m "메세지"` : `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장

<br>

### ✅ 원격저장소에 업로드하기
#### ✔️ remote add
- `git remote add <원격저장소이름> <원격저장소URL>` : 원격저장소URL을 <원격저장소이름>으로 저장
#### ✔️ push
- `git push <원격저장소이름> <브랜치이름>` : 원격저장소에 브랜치를 업로드
- 보통 원격저장소이름 : origin\
브랜치이름 : master (mac은 main)

<br>

### ✅ 원격저장소 공유
- 공유메일 전송 :  Git - Settings - Collaborators - Add people - user name

#### ✔️ clone
- `git clone <원격저장소URL>` : 개인서버로 폴더 복제 

#### ✔️ pull
- `git pull <원격저장소이름> <브랜치이름>` : 원격저장소 새로운 데이터 불러오기

#### ✔️ merge
- code 수정사항 반영(병합)
- github에서 `merge pull request`를 통해 최종 반영

<br>

### ✅ 충돌이 일어나는 경우
- 원격저장소 파일과 개인서버 파일의 차이가 생겨 `push`를 해도 작동이 일어나지 않음
- git의 최신 파일로 작업하지 않았을 경우 발생
![error](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FPMIYB%2FbtsDp6JoWkX%2FSxLIC9dXeIM3q3fLyNfUcK%2Fimg.png)

- 따라서 원격저장소 최신 파일을 `pull`해서 재작업해야 할 수 있음
- 강제로 `push`하는 방법이 있으나 저장된 파일이 날라갈 수 있음

<br>

### ✅ 팀프로젝트할 때 기본 작업루틴
```
1. 최신 데이터 가져오기
    - `git switch main`
    -> `git pull origin main`
    -> `git switch <내 브랜치>`
    -> `git merge main`

2. 작업 진행
    - `git switch <내 브랜치>`
    -> 작업
    -> `add / commit / push`

3. github에서 `pull request` -> `merge`
```