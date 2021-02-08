# git 기본

## Merge

remote repository 로부터 local repository 로 pull 한 내용이 최신 버전이 아닌 경우 (내가 pull 한 이후로 다른 사람이 push 로 새로운 내용을 업데이트 했을 경우) 나의 push 요청이 거부된다.

![push_error](/picture/push_error.png)

이때 merge 를 통해 다른 사람의 업데이트 내역을 내 local repository 에도 갱신한다. 

![nessesary_merge](/picture/nessesary_merge.png)

> merge 하지 않은 채로 push 를 하면 다른 사람의 push 내역이 사라져 버린다

## 충돌 해결

merge 가 자동으로 병합해주지만 그렇지 못한 부분이 존재한다. 바로 remote repository 에서 변경된 곳과 local repository 에서 변경된 곳이 같은 경우다. 이러한 경우는 직접 고쳐줌으로써 해결할 수 있다.

![collision_in_merge](/picture/collision_in_merge.png)

>local repository 변경 내용
>
>====
>
>remote repository 변경 내용

![revise_collision](/picture/revise_collision.png)

