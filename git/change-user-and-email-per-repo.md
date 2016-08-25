# git user.name, user.email 를 repo 별로 설정하기
git을 사용하는 시스템에서 대체로 전역적으로 `user.name` 과 `user.email`를 설정해서 사용하는 경우가 많다.
```shell
git config --global user.name "NAME"
git config --global user.email "NAME@MAIL"
```

회사에서 일을 하다보면 개인 저장소에 commit를 할 경우가 발생한다. 대체로 회사에서 사용하는 이름과 email 이 git 의 기본 설정으로 되어 있다.
개인 저장소에서는 다른 이름을 하고 싶다면 아래와 같이 하면 된다.
```shell
cd $LOCAL_REPO
git config user.name "NAME"
git config user.email "NAME@MAIL"
```

또는 해당 저장소의 `.git/config` 파일에 아래의 구문을 추가한다.
```shell
[user]
    name = NAME
    email = NAME@MAIL
```
