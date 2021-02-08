# git 기본

git 을 간단하게 이용해보자

## 초기 설정

git 설정내역은 .gitconfig 파일에 기록된다. (vi ~/.gitconfig 콘솔에서 실행해보면 설정한 내용들이 기록되어 있음)

> .gitconfig 파일에 직접 기록해서 설정 가능
>
> git config 명령어로 설정 가능

```bash
git config --global user.name "name"
git config --global user.email "mail"

# git 출력 메세지 색상 설정
git config --global color.ui auto

# git 단축기(alias) 설정 가능 : checkout -> co
git config --global alias.co checkout
```

## 새 저장소 만들기

```bash
# git repository 로 만들 폴더로 가서 수행한다
git init
```

```bash
mkdir tutorial
cd tutorial
git init
```

## Push

remote repository 로 변경된 파일을 업로드하는 것

## Clone

remote repository 의 내용들을 통째로 다운로드하는 것

> 변경 이력도 함께 local repository 로 복제되어 오므로, remote repository 와 똑같이 이력을 참조하고 커밋을 진행할 수 있다

## Pull

remote repository 를 공유해 여러 사람이 함께 작업을 한다. 다른 사람이 push 를 통해 변경한 내용들을 나의 local repository 에도 적용하기 위해 업데이트하는 것