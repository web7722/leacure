# WSL2 git 설정하기 

**참고하기**
> http://pinedance.github.io/blog/2021/02/07/WSL-git-keychain


## setting

원격 저장소 설정하기


## 1. .gitignore 알아보기

.gitignore 파일의 역활은
필요에따라. 우리의 git로 관리하는 디렉토리 안에서 
git으로 관리하고 싶지 않은 파일을 만들때 생성합니다.
사용하는방법은 

프로젝트 루트 디렉토리에 .gitignore 파일을 생성합니다.
이후 파일에 

.env 라고 적어보고
프로젝트 폴더 안에서 .env 파일을 생성하고
이후에 PORT=3000이라는 텍스트를 적어봅시다.

혹시 올리고싶지 않은 파일을 github에 올렸다면
삭제를 하고싶을경우..

```
git rm -r [file Name] # 원격 저장소 및 로컬 저장소 파일을 삭제
git rm --cached -r [File Name] # 원격 저장소에 있는 파일 삭제
```

git status 를 활용하여 내용을 확인해보시면 더욱좋습니다.

이후 .gitignore 안에서 패턴을 또 아셔야합니다!
프로젝트 내용마다 무시할 파일이나 또는 폴더가존재합니다.
저희같은경우 node_module 폴더는 어지간하면 보내면안됩니다.
그리고 또 package-lock.json 또한 보내면안됩니다.

gitignore 형식은

```
file.js # 모든 file
/file.js # 최상위 디렉토리에 있는 file
*.js # 모든 .js파일
node_modules # node_modules 라는 파일이름 또는 폴더와 그하위내용들

이정도만 알고넘어가도 괜찮을거에요
```

## 2. 이전내역으로 돌아가기 (Reset , Revert)

돌아가기 위해서는 git 가 어떻게 저장되는지 알아볼 필요가있어요.
```
git log #활용하여 내가 저장한 히스토리 들을 확인할수있습니다.
이후 j를 누르면 내릴수있습니다.
```

하지만 이번수업에서는 간단하게 볼수있는 git Graph 를 활용할거에요.

간단히 git log 를 조금더 UI적으로 표현해준다고 보면됩니다.

이후 자신 로컬에있는 저장소와 github에 있는 커밋히스토리와 비교해보세요.

이제는 과거 코드를 보는것을 해볼거에요

Reset 과 Revert 차이를 알아볼게요

Reset은 돌아가는 목적지까지 내용을 지우는 행위입니다.
Revert는 돌아가는 목적지까지 내용을 새로 커밋하는 행위입니다.

```
git reset --hard [돌아갈 커밋hash]
```



```
git revert [돌아갈 커밋hash]
```

하게될경우 commit 만 쓸경우 나왓던 내용이 나옵니다.

