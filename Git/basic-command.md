# basic command
> git 기본 문법 정리

## 초기 설정
- git을 설치 후 한번만 실행
```bash
git config --global user.email <이메일>
git config --global user.name <이름>
```

## git 저장소 만들기

![distribute](./image/distributed.png)

- `git init`
    - `.git directory`를 생성해주는 명령어
    - 관리하고 싶은 최상위 위치에서 실행

## git 상태 체크
- `status` : 현재 git으로 관리되고 있는 파일/폴더의 상태를 출력

## 코드 수정하고 저장소에 저장하기

- `add`
     - `git add <파일/폴더이름>` : `working directory`에서 `staging area`로 추가
     - `git add .` : 일반적으로 모든 파일, 폴더를 추가하기 위해 <.>을 사용

- `comit`
    - `git commit -m "메세지"`
    - `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장
    - 일반적으로 `-m`옵션을 넣어서 메세지를 추가하여 등록

## 원격저장소에 업로드하기

![cycle](./image/lifecycle.png)

- `remote add`
    - `git remote add <원격저장소이름> <URL>` : 원격저장소 주소를 <원격저장소이름>으로 저장

- `push`
    - `git push <원격저장소이름> <브랜치이름>` : 원격저장소에 브랜치를 업로드
    - 보통 원격저장소이름 : origin
    브랜치이름 : master (mac은 main)


## 원격저장소 공유


- 공유메일 전송 :  Git - Settings - Collaborators - Add people - user name

- `clone` : 개인서버로 폴더 복제
    1. mac template 열기 
    2. `cd` 이용해 폴더 이동 
    3. `git clone <URL>`

- 수정 후 `push` 이용해 원격저장소 저장

- `pull` : 원격저장소 새로운 데이터 불러오기
    - `git pull <원격저장소이름> <브랜치이름>`

>충돌이 일어났을 경우
- 코드의 차이가 생겨 `push`를 해도 작동이 일어나지 않음
- git의 최신 파일로 작업하지 않았을 경우 발생할 수 있음
![error](./image/스크린샷%202023-09-26%20오후%2011.04.59.png)

>오류 해결방법 
- `pull` - `Auto-merging` 활성화
![solution](./image/스크린샷%202023-09-26%20오후%2011.14.04.png)

[git reference](https://github.com/yoogeon97/end-to-and.git)

## Branch 
- `branch` : master server를 이루기 위한 기능별 server (충돌방지)
    - `git branch`
    - `git branch -c <브랜치이름>`
    - `git switch <브랜치이름>`
    - New file 생성
- git hub 공유
    - `pull request`
    - `new pull request`
    - master - base 선택
    - `create pull request` : code review 요청 글 작성
- `merge` : code 수정사항 반영
    - `merge pull request`
        - 개발자 각자의 코드를 반영할 때 충돌 발생할 수 있음
        - `resolve conflict`를 이용하여 conflict 발생한 코드 중 코드를 선택 -  `mark resolved` - `commit merge`

[git reference](https://github.com/camp31/backiljang.git)
