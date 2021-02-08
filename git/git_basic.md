git 공부를 위해 여기 사이트에서 공부하고 정리 [git 입문 공부](https://backlog.com/git-tutorial/kr/intro/intro1_1.html)

# git 기본

- git 을 맛보기로 배워보자. 
- 전체적인 내용을 공부한다.

## Git

<u>소스코드를 효과적으로 관리</u>하기 위해 개발된 '분산형 버전 관리 시스템'

- 소스 코드가 변경된 이력을 쉽게 확인
- 특정 시점에 저장된 버전과 비교
- 특정 시점으로 돌아가기 가능
- 편집한 내용이 다른 사람과 충돌한다면, 경고 메세지 발생
- •••

등등 수많은 역할을 한다. ~~차차 배워나가보자~~

> Git으로 파일을 관리하면, 업데이트 이력이 Git에 저장되서 따로 백업용 파일을 만들 필요가 없다

---

## Repository

파일, 폴더를 저장해 두는 곳

- **파일의 변경 이력 별로 구분되서 저장됨** => 비슷한 파일일지라도 실제 내용 일부 문구가 서로 다르면 다른 파일로 인식하기 때문에 파일을 변경 사항 별로 구분해 저장할 수 있음

### Two kinds

Git은 두 종류의 Repository를 지원한다

- **Remote Repository** : 파일이 Remote Repository 전용 서버에서 관리되며 여러 사람이 함께 공유하기 위한 저장소
- **Local Repository** : 내 PC에 파일이 저장되는 개인 전용 저장소

> local repository 에서 작업하다가 작업한 내용을 공개하고 싶을 때에 remote repository 에 업로드한다.
>
> 반대로 remote repository 에서 다른 사람들이 공유한 내용을 내 local repository 로 가지고 올 수 있다.

![repository](/picture/repository.png)

---

## Commit

파일 및 폴더의 추가/변경 사항을 repository 에 기록한다. **변경 이력을 남긴다**

> 버그 수정, 기능 추가 등 특별한 의미가 있는 업데이트를 작업 별로 구분해서 각각 커밋하면, 기록된 이력을 보고 특정 변경 내용을 찾기 쉽다

commit 은 변경 이력을 남기는 중요한 작업이기 때문에 commit message 는 필수적이다. (어떤 것을 변경했는지 알려주는... git 은 기본적으로 협업을 위한 시스템이기 때문에 나 뿐만 아니라 타인들도 쉽게 알 수 있도록 해야한다.)

### Git 에서 권장하는 commit message 형식

![format_commit_message](/picture/format_commit_message.png)

---

## Work tree , Index

- work tree : 폴더
- index : commit 실행하기 전의 repository 와 work tree 사이에 존재하는 공간

![index](/picture/index.png)

---

commit 은 work tree 에 있는 변경 내용을 repository 에 바로 기록하는 것이 아니라 index 에 기록(**stage**)한다. 그리고 repository 에 변경 내용을 기록하기 위해서는 그 내용이 index 에 존재해야한다.

index 에 기록(**stage**)하는 단계가 있기 때문에 commit 이 필요 없는 파일들을 포함하지 않을 수 있고, 파일에서 일부 변경 사항만 index 에 기록후에 commit 할 수 있다.