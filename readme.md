# TIL

### 2022-09-21

## 0. 시작
- git bash 사용시 windows 운영체제의 사용자 이름은 **영어**로 설정하기
- 관리자 권한으로 실행하기! 

## 1. 리눅스 커맨드 기초
### 명령어

```
pwd : print working directory
```

```
cd : change directory
```
- cd /c : 절대경로
- cd /c/경로1/경로2 : 경로 ㅈ로 가겠다는 것 /c가 아닌 것은 상대경로 
- cd .. : 상위 경로로 가는 명령어 
- cf) 경로 기재시 tab키로 폴더명 자동완성 가능

```
ls : list
- 현재 작업 경로에 있는 파일, 폴더 목록 알 수 있는 명령어
```
- ls 뒤에는 -a나 -l 옵션을 붙일 수 있다.

```
clear : bash 화면 지우기
```

```
history : 사용했던 명령어 모두 확인 가능
```

```
~ : root directory로 가는 것
```

## 2. vim 사용
### 일반적인 vim

- 윈도우에서 git bash를 설치할 때 default editor로 vim을 세팅/선택했기 때문에 git 사용하려면 반드시 vim을 사용할 줄 알아야 함.
- git bash에서 vim 파일명.확장자명으로 생성
- 파일 생성시 vim editor 켜짐
- 최초 명령모드 진입 `i` 눌러 입력모드 진입 -> 내용 입력 -> `esc` (명령모드 진입) -> `:wq` (write and quit)
- **최소한 vim으로 파일 수정하는 것 알아야 git 다룰 수 있다.**

### vim의 예외상황

- 잘못해서 vim을 닫았을때 (저장하지 않고 껐을 때) -> swap파일 만들어 졌을 때 가정
- 에러 문구 확인될 시 관련 문구마다 해결 방법 나오니 맞게 처리하면 됨 
- 예) 수정한 것 저장 하지 않고 껐을 때 -> `.swp` 파일 삭제 후 -> `R` 명령어 입력 -> 파일 다시 열기

## 3. Gitignore
- 커밋에 포함하고 싶지 않은 파일 관리 (예. 보안키, id/pw등)
- 새로운 repository 만들면 반드시 추가 해야함
- gitignore generator로 검색 후 파일 만들어 커밋하거나 repository 만들때부터 gitignore 옵션 선택

## 4. branch
- 혼자 작업시 브랜치 안만들어도 됨
- 같이 작업시에는 무조건 만들어야 함.
    - 기능추가
    - 버그 수정 등을 위함


## 5. 커밋
### 커밋의 기본

- 커밋의 정의
  - The "commit" command is used to save your changes to the local repository.
  - The git commit command captures a snapshot of the project's currently staged changes.
    스냅샷과 유사함 

- git의 기본 단위
    - 커밋 하나는 독립적인 버전을 나타냄
    - 커밋마다 설명이 담긴 message가 있음
- 얼마나 자주 커밋을 만들어야 하는가?
    - 커밋 크기가 작을수록 좋음→ 롤백이 쉬워지기 때문에
    - **one commit per logical change** → 유의미한 논리적 변경이 있을 때 커밋
    - 회사에서 일할때는 동료들이 커밋한 이력을 보고 어느 정도의 단위로 커밋하는지 확인 해보면 됨.
  
### 커밋 만들기
    
- 커밋 만들기
    - 현재 디렉터리로 이동
        - `git commit -m “커밋 메시지”`
        - `git log` 입력하여 이력에 커밋 나타나는지 확인하기
        - `git status` 입력하여 상태 확인하기
  
### 커밋 방법
- 커밋 메시지: 해당 커밋에서 어떤 변경이 있었는지를 설명하는 메시지
    - 좋은 커밋 메시지란?
        - [https://github.com/javascript-tutorial/ko.javascript.info/pull/460](https://github.com/javascript-tutorial/ko.javascript.info/pull/460)
- 명령창에 `git commit -m “커밋 메시지”`
- `git commit —message “커밋 메시지”`
- `이슈트래커` 사용 e.g. Jira, canban note
    
    레파지토리에서 issue → new issue → 기재 후 해결 ⇒ **이슈트래커 사용!!**
    
    - 개발세계에서의 issue는 해결해야할 task 라는 의미
    - issue 마다 고유한 번호가 붙음
    - git commit → 엔터 → 빈 에디터 혹은 vscode등 설정사항 → 최 상단에 (line1) 커밋 메시지 입력 → **두번째 줄은 반드시 공백으로 남기기 (제목과 본문을 한 줄 띄워 분리하기!)**
    - 혹은 커밋 메시지 안에 #이슈번호를 기재해야 한다. (깃 프로그램마다 방법 다름)

## 기타
★ 회사에서는 누구도 main branch에 하지 않는다. 

> Q. git push -u origin main vs git push origin main
> A. git push -u origin main은 원격저장소와 로컬저장소 연동할 때, 지금 체크아웃하는 모든 커밋을 origin이라는 저장소의 main 브랜치에 저장하겠다.라는 명령어인거고, 그 안에서도 -u는 두 저장소 간의 브랜치끼리도 통신 가능하게 해주는 명령어

